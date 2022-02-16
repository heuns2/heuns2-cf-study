# Pivotal Cloud Foundry Feature Flags 종류
- CF (Cloud Foundry) 관리자가 Cloud Foundry Command Line Interface (cf CLI)를 사용하여 Feature Flags를 설정하여 사용자가 사용할 수있는 기능을 Enable 시키는 방법에 대해 작성하였다.


## 1. View and Edit Feature Flags  
- 사용자가 사용할 수있는 Feature Flags를 확인하는 방법은 아래와 같다.

```
$ cf feature-flags
Retrieving status of all flagged features as pcfadmin...

features                                      state
user_org_creation                             disabled
private_domain_creation                       enabled
app_bits_upload                               enabled
app_scaling                                   enabled
route_creation                                enabled
service_instance_creation                     enabled
diego_docker                                  enabled
set_roles_by_username                         enabled
unset_roles_by_username                       enabled  
task_creation                                 enabled
env_var_visibility                            enabled
space_scoped_private_broker_creation          enabled
space_developer_env_var_visibility            enabled
service_instance_sharing                      enabled
hide_marketplace_from_unauthenticated_users   disabled
```

## 2. Enable/Disable Feature Flags
- enable-feature-flag 방법 예시
```
$ cf enable-feature-flag user_org_creation
```

- disable-feature-flag 방법 예시
```
$ cf disable-feature-flag user_org_creation
```

## 3. Feature Flags 종류

- `user_org_creation`:  PAS 상의 모든 사용자에 대해 Org 생성 기능을 활성화 한다. Enable 시 Apps Manager UI에 Org 생성 Dropdown 메뉴가 생긴다.
- `private_domain_creation`: Org에 대한 권한이 있는 사용자는 해당 Org에 Private Domain을 생성 할 수 있다.
- `app_bits_upload`: Space에 대한 권한이 있는 사용자는 해당 Space의 Application에 Bit를 업로드 할 수 있다.
- `app_scaling`: Space에 대한 권한이 있는 사용자는 해당 Space의 Application Auto Scaling을 실행 할 수 있다.
- `route_creation`: Space에 대한 권한이 있는 사용자는 해당 Space에 Route를 생성 할 수 있다.
- `service_instance_creation`: Space에 대한 권한이 있는 사용자는 해당 Space에 Service Instance를 생성 할 수 있다.
- `diego_docker`: Space에 대한 권한이 있는 사용자는 해당 Space에 Docker Image를 Push 할 수 있다.
- `set_roles_by_username`: Org/Space에 대한 권한이 있는 사용자는 사용자 명으로 Role을 추가 할 수 있다.
- `unset_roles_by_username`: Org/Space에 대한 권한이 있는 사용자는 사용자 명으로 Role을 해제 할 수 있다.
- `task_creation`: Space에 대한 권한이 있는 사용자는 해당 Space의 Application Task를 생성 할 수 있다.
- `env_var_visibility`: 모든 사용자는 Application의 환경 변수를 확인 할 수 있다.
- `space_scoped_private_broker_creation`: Space에 대한 권한이 있는 사용자는 해당 Space 범위의 Service Broker를 생성 할 수 있다.
- `space_developer_env_var_visibility`: Org/Space에 대한 권한이 있는 사용자는 v2/v3의 환경 변수를 확인 할 수 있다.
- `service_instance_sharing`: Space에 대한 권한이 있는 사용자는 서로 다른 2개의 Space 사이에서 Service Instance를 공유 할 수 있다.
- `hide_marketplace_from_unauthenticated_users`: 인증 되지 않은 사용자에게 Marketplace의 정보를 숨긴다.
