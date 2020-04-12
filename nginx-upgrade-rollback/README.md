# nginx-upgrade-rollback

This README talks about helm release upgrade and rollback.

Once chart is released, it is very natural to upgrade it as we bring in new changes. Be it a docker 
image tag change or ingress URL change or any other change.

It is also natural to rollback the release in case something goes wrong and recent release results 
into application failure.

### Upgrade release

- Install chart [nginx-template](../nginx-template)

- Let's make change to `nginx-template` chart, change path in `values.yaml` to `/nginx-template-upgrade`

- Run below command to upgrade `nginx-template`
  
  `$ helm upgrade nginx-template nginx-template`
  
- Take a look at helm release, `$ helm list --filter nginx-template`

  ```text
  NAME          	NAMESPACE	REVISION	UPDATED                             	STATUS  	CHART               	APP VERSION
  nginx-template	default  	2       	2020-04-12 11:34:39.676965 +0100 BST	deployed	nginx-template-0.1.0	1.16.0     
  ```
  Notice `REVISION` column, the revision of release has bumped.
  
### Rollback release

- We have install and upgraded `nginx-template` as mentioned in [Upgrade release](###Upgrade release)
  
- Let's rollback the recent release, `$ helm rollback nginx-template 1`

- Take a look at helm release again, `$ helm list --filter nginx-template`
  ```text
  NAME          	NAMESPACE	REVISION	UPDATED                             	STATUS  	CHART               	APP VERSION
  nginx-template	default  	3       	2020-04-12 11:39:43.310148 +0100 BST	deployed	nginx-template-0.1.0	1.16.0     
  ```
  Notice `REVISION` column, the revision of release has bumped. So rollback also results into release version bump.
  
- To get more insights on revision, check helm history `$ helm history nginx-template`
  ```text
  REVISION	UPDATED                 	STATUS    	CHART               	APP VERSION	DESCRIPTION     
  1       	Sun Apr 12 11:33:26 2020	superseded	nginx-template-0.1.0	1.16.0     	Install complete
  2       	Sun Apr 12 11:34:39 2020	superseded	nginx-template-0.1.0	1.16.0     	Upgrade complete
  3       	Sun Apr 12 11:39:43 2020	deployed  	nginx-template-0.1.0	1.16.0     	Rollback to 1
  ```