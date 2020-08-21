# gitlab license keygen role

Use for testing or education only

```
---
- hosts: gitlab-host
  become: true
  roles:
  - ansible-gitlab
  vars:
    admin_api_token: "your_admin_token"
    gitlab_domain: gitlab.example.com
    license_plan: ultimate #gold, silver, ultimate
    license_name: TestUser
    license_company: Testing LLC
    license_email: test@example.com
```

After successful license loading license page always responses with 500 status - it's ok.
If you want to check current license, you can get it through api request:

`curl  --header "Private-Token: <your_admin_token>" https://gitlab.example.com/api/v4/license/`

Also, `ultimate` licensing plan can be checked through availability Geo and some Epics functionality.

If something gets wrong - you can delete license through api request:
`curl --request DELETE --header "Private-Token: <your_admin_token>" https://gitlab.example.com/api/v4/license/<license_id>`