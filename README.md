# Lucky-Books-Analyze

> 도서관 데이터에 대한 전처리 및 Analyze 레파지토리입니다.  
> data_to_db.ipynb에는 데이터 전처리 및 MongoDB 셋업 과정이 있습니다.  

## 데이터 초기화 방법(MongoDB Backup 사용)  
```bash
mongorestore --db luckybooks /workspace/data/database/{날짜}
```
예시:  
```bash
mongorestore --db luckybooks /workspace/data/database/240726
```