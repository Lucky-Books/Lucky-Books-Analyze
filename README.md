# Lucky-Books-Analyze

> 도서관 데이터에 대한 전처리 및 Analyze 레파지토리입니다.  
> data_to_db.ipynb에는 데이터 전처리 및 MongoDB 셋업 과정이 있습니다.  

## 도커 이미지 빌드 및 컨테이너 생성 방법  
도커 이미지 빌드:  
```bash
cd docker
docker build -t luckybooks .
```
도커 컨테이너 생성:  
```bash
docker run -it --shm-size=5G --name=luckybooks -v {레파지토리를 다운로드한 경로}/data:/workspace/data {레파지토리를 다운로드한 경로}/src:/workspace/src -p 27017:27017 luckybooks
```

컨테이너를 생성하여 구동하면 /workspace 경로로 들어가면 됨.  
해당 컨테이너에서 작업한 내용은 본인 컴퓨터의 레파지토리 경로에 자동으로 동기화됨.

## 데이터베이스 초기화 방법(MongoDB Backup 사용)  
```bash
mongorestore --db luckybooks /workspace/data/database/{날짜}
```
예시:  
```bash
mongorestore --db luckybooks /workspace/data/database/240726
```

## 변경한 데이터베이스 업로드 방법
```bash
mongodump --db luckybooks --out /workspace/data/database/{날짜}
```
예시:  
```bash
mongodump --db luckybooks --out /workspace/data/database/240726