# AWS

## AWS cli

AWS 명령줄 인터페이스(CLI)는 AWS 서비스를 관리하는 통합 도구입니다. 도구 하나만 다운로드하여 구성하면 여러 AWS 서비스를 명령줄에서 제어하고 스크립트를 통해 자동화할 수 있습니다.

### 사전 준비

- [aws credential 설정](https://docs.aws.amazon.com/ko_kr/cli/latest/userguide/cli-chap-configure.html)
- [aws-cli 설치 및 구성](https://docs.aws.amazon.com/ko_kr/streams/latest/dev/kinesis-tutorial-cli-installation.html)

### 사용 예시

```bash
aws s3 cp <local file path> s3://<bucket-name>/<key> # local에 있는 file을 s3로 복사
```

## AWS service

- [EC2](https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/concepts.html)
Amazon Elastic Compute Cloud(EC2)는 안전하고 크기 조정이 가능한 컴퓨팅 파워를 클라우드에서 제공하는 웹 서비스입니다. 

- [ELB](https://aws.amazon.com/ko/elasticloadbalancing/)
Elastic Load Balancing은 단일 가용 영역 또는 여러 가용 영역에서 다양한 애플리케이션 부하를 처리할 수 있습니다.

- [Auto Scling](https://docs.aws.amazon.com/ko_kr/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)
AWS Auto Scaling은 애플리케이션을 모니터링하고 용량을 자동으로 조정하여, 최대한 저렴한 비용으로 안정적이고 예측 가능한 성능을 유지합니다.

- [VPC](https://docs.aws.amazon.com/ko_kr/vpc/latest/userguide/what-is-amazon-vpc.html)
AWS 클라우드에서 논리적으로 격리된 공간을 프로비저닝하여 고객이 정의하는 가상 네트워크에서 AWS 리소스를 시작할 수 있습니다.

- [IAM](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/introduction.html)
AWS Identity and Access Management(IAM)는 AWS 리소스에 대한 액세스를 안전하게 제어할 수 있는 웹 서비스입니다.

- [S3](https://docs.aws.amazon.com/ko_kr/AmazonS3/latest/dev/Welcome.html)
Amazon Simple Storage Service(Amazon S3)는 객체 스토리지 서비스입니다.

- [ECS](https://docs.aws.amazon.com/ko_kr/AmazonECS/latest/developerguide/Welcome.html)
Amazon Elastic Container Service(ECS)는 확장성이 뛰어난 고성능 컨테이너 오케스트레이션 서비스로서, Docker 컨테이너를 지원하며 AWS에서 컨테이너식 애플리케이션을 쉽게 실행하고 확장 및 축소할 수 있습니다.

- [ECR](https://docs.aws.amazon.com/ko_kr/AmazonECR/latest/userguide/docker-basics.html)
Amazon Elastic Container Registry(ECR)는 개발자가 Docker 컨테이너 이미지를 손쉽게 저장, 관리 및 배포할 수 있게 해주는 완전관리형 Docker 컨테이너 레지스트리입니다.

- [CodePipeline](https://docs.aws.amazon.com/ko_kr/codepipeline/latest/userguide/welcome.html)
AWS CodePipeline은 빠르고 안정적인 애플리케이션 및 인프라 업데이트를 위해 릴리스 파이프라인을 자동화하는 데 도움이 되는 완전관리형 지속적 전달 서비스입니다.

- [CodeBuild](https://docs.amazonaws.cn/en_us/codebuild/latest/userguide/welcome.html)
AWS CodeBuild는 소스 코드를 컴파일하는 단계부터 테스트 실행 후 소프트웨어 패키지를 개발하여 배포하는 단계까지 마칠 수 있는 완전관리형의 지속적 통합 서비스입니다.

- [CodeDeploy](https://docs.aws.amazon.com/ko_kr/codedeploy/latest/userguide/welcome.html)
AWS CodeDeploy는 Amazon EC2, AWS Fargate, AWS Lambda 및 온프레미스 서버와 같은 다양한 컴퓨팅 서비스에 대한 소프트웨어 배포를 자동화하는 완전관리형 배포 서비스입니다.

## Reference

- [aws cli](https://aws.amazon.com/ko/cli/)