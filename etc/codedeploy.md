# CodeDeploy

## service 역할

### EC2/온프레미스 배포의 경우

AWSCodeDeployRole 정책을 연결합니다.

AWSCodeDeployRole정책에 연결된 권한

- 인스턴스의 태그를 읽거나 Amazon EC2 Auto Scaling 그룹 이름으로 Amazon EC2 인스턴스를 식별합니다.	
- Amazon EC2 Auto Scaling 그룹, 수명 주기 후크 및 조정 정책을 읽고 생성하고 업데이트하고 삭제합니다.
- Amazon SNS 주제에 정보를 게시합니다.
- CloudWatch 경보에 관한 정보를 검색합니다.
- Elastic Load Balancing를 읽고 업데이트합니다.
    - 시작 템플릿으로 Auto Scaling 그룹을 생성한 경우 다음 권한을 추가해야 합니다.
        - ec2:RunInstance
        - ec2:CreateTags
        - iam:PassRole

### AppSpec file

- EC2/온프레미스 컴퓨팅 플랫폼을 사용하는 경우 AppSpec file의 이름은 항상 appspec.yml이어야 합니다.(json X)
- 애플리케이션 소스 코드 디렉터리 구조의 루트에 저장해야 합니다. 그렇지 않으면 배포에 실패합니다.
- AppSpec file을 완성한 후 배포할 콘텐츠와 함께 아카이브 파일(zip, tar 또는 압축 tar)로 번들링합니다.

```yaml
version: 0.0
os: linux
files:
  - source: /
    destination: /var/www/html/WordPress
hooks:
  BeforeInstall:
    - location: scripts/install_dependencies.sh
      timeout: 300
      runas: root
  AfterInstall:
    - location: scripts/change_permissions.sh
      timeout: 300
      runas: root
  ApplicationStart:
    - location: scripts/start_server.sh
    - location: scripts/create_test_db.sh
      timeout: 300
      runas: root
  ApplicationStop:
    - location: scripts/stop_server.sh
      timeout: 300
      runas: root
```

#### files

- 배포의 Install 이벤트 중 인스턴스에 설치되어야 하는 애플리케이션 개정의 파일에 대한 정보를 CodeDeploy에 제공합니다.
- 이 섹션은 배포 중 개정의 파일을 인스턴스의 위치로 복사하는 경우에만 필요합니다.
- source
    - **source**가 파일을 나타내는 경우 지정한 파일만 인스턴스로 복사됩니다.
    - **source**가 디렉터리를 나타내는 경우 디렉터리 내의 모든 파일이 인스턴스로 복사됩니다.
    - **source**가 슬래시 하나인 경우(Amazon Linux, RHEL 및 Ubuntu Server 인스턴스의 경우: “/“, Windows Server 인스턴스의 경우: “\”) 개정의 모든 파일이 인스턴스로 복사됩니다.

#### [hooks](https://docs.aws.amazon.com/ko_kr/codedeploy/latest/userguide/reference-appspec-file-structure-hooks.html#appspec-hooks-server)