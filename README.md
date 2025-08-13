# gitlab-proxy
A proxy for gitlab.com that only allows access to specific projects

This project allows you to setup a http(s) reverse proxy in front of public/cloud GitLab, and use it for git push/pull. 

Advantages:
* You can hardcode a (Personal|Project|Group) access token in the nginx config, which means end users do not need any authentication to push/pull
* You can limit access to GitLab to specific groups/subgroups/projects by tweaking the nginx config to deny all others. (This also depends on blocking direct access to gitlab.com)

Example:
```
docker compose up -d
# works!
git clone http://localhost:8080/gitlab-org/api/client-go


#blocked!
git clone http://localhost:8080/gitlab-org/gitlab.git
```