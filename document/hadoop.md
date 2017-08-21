Hadoop
==================

1. 실습 데이터(영국 교통사고 데이터) 다운로드

> 사고 이력 : https://github.com/skholdings/hadoop_lecture/raw/master/sample_data/DfTRoadSafety_Accidents.zip

> 사상자 정보 : https://github.com/skholdings/hadoop_lecture/raw/master/sample_data/DfTRoadSafety_Casualties.zip

> 지역 코드 : https://github.com/skholdings/hadoop_lecture/raw/master/sample_data/DfTRoadSafety_District.zip

> 데이터 활용 가이드 : http://github.com/skholdings/hadoop_lecture/raw/master/sample_data/Road-Accident-Safety-Data-Guide.xls

<br>

2. 압축 해제

> unzip DfTRoadSafety_Accidents.zip

> unzip DfTRoadSafety_Casualties.zip

> unzip DfTRoadSafety_District.zip

<br>

3. HDFS에 파일 업로드

> (Local) Accidents_*.csv  ->  (HDFS) /input/acc

> (Local) Casualties_*.csv  ->  (HDFS) /input/cas

> (Local) District.txt  ->  (HDFS) /input/dis

<br>

4. MapReduce Application 다운로드

> http://github.com/skholdings/hadoop_lecture/raw/master/build/hadoop_ex01.jar

> http://github.com/skholdings/hadoop_lecture/raw/master/build/hadoop_ex02.jar

> http://github.com/skholdings/hadoop_lecture/raw/master/build/hadoop_ex03.jar

<br>

5. Driver Class의 실행 (실습 1)

>hadoop jar hadoop_ex01.jar -D inputPath=/input/acc/* -D outputPath=/output/result01 -D numReduceTasks=3 skill.coach.TestDriver

<br>

6. Driver Class의 실행 (실습 2)

>hadoop jar hadoop_ex02.jar -D inputPath=/input/acc/* -D outputPath=/output/result02 -D numReduceTasks=3 skill.coach.TestDriver

<br>

7. Driver Class의 실행 (실습 3)

>hadoop jar hadoop_ex03.jar -D inputPath1=/input/acc/* -D inputPath2=/input/cas/* -D cachePath=/input/dis/District.txt -D tempPath=/output/result03_1 -D outputPath=/output/result03_2 -D numReduceTasks=10 skill.coach.TestDriver
