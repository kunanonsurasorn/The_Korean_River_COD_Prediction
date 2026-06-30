# **โปรเจกต์การคาดการณ์ Chemical Oxygen Demand (COD) โดยใช้ชุดข้อมูลคุณภาพแม่น้ำนักดงในประเทศเกาหลีใต้**

## 1. วัตถุประสงค์ 

     1.1 เพื่อพัฒนาโมเดลสำหรับการคาดการณ์ Chemical Oxygen Demand ที่เหมาะสม

     1.2 เพื่อพัฒนาการเขียนโปรแกรมสำหรับการค้นหาโมเดลที่เหมาะสมโดยใช้ GridSearchCV

## 2. ชุดข้อมูล

     2.1 ชุดข้อมูลที่ใช้มาจากหน่วยงานสถิติของประเทศเกาหลีใต้ (Korean Statistical Information Service) 
 
     2.2 เว็บไซต์ของหน่วยงานสถิติเกาหลีใต้ : https://kosis.kr/eng/

## 3. ภาษาที่ใช้ในการเขียนโปรแกรม

     3.1 ภาษาที่ใช้ในการเขียนโปรแกรมคือ Python
     
     3.2 ซอฟต์แวร์ที่ใช้ในการเขียนโปรแกรมคือ Google Colab

## 4. Python Libraries ที่ใช้ในการทำโปรเจกต์

     4.1 Pandas
 
     4.2 Matplotlib
 
     4.3 Seaborn
 
     4.4 Sklearn

## 5. โมเดลที่ใช้สำหรับค้นหาโมเดลที่เหมาะสม

     5.1 Linear Regression
 
     5.2 Ridge Regression
 
     5.3 Lasso Regression
 
     5.4 Support Vector Machine

     5.5 K-Nearest Neighbors

     5.6 Decision Tree

## 6. วิธีการประเมินโมเดลสำหรับการคาดการณ์

     6.1 Mean Absolute Error (MAE)
 
     6.2 Mean Squared Error (MSE)
 
     6.3 Coefficient of determination (R-Squared)

## 7. Data Visualization ที่ใช้ในการดูข้อมูล

     7.1 Box Plot

![MIS2023PIC02.png](https://github.com/kunanonsurasorn/The_Korean_River_COD_Prediction/blob/main/MIS2023PIC02.png)

![MIS2023PIC03.png](https://github.com/kunanonsurasorn/The_Korean_River_COD_Prediction/blob/main/MIS2023PIC03.png)
     
     7.2 Correlation Heatmap

![MIS2023PIC01.png](https://github.com/kunanonsurasorn/The_Korean_River_COD_Prediction/blob/main/MIS2023PIC01.png)

## 8. ผลลัพธ์ของโมเดลการคาดการณ์ COD จากชุดข้อมูลคุณภาพน้ำของแม่น้ำนักดงในเดือนมิถุนายนถึงสิงหาคมระหว่างปี 2017 - 2020

     |                             MODEL                       |     MAE      |     MSE     |     
     8.1 LinearRegression()                                         0.7981         1.2196    
     8.2 Ridge(alpha = 1)                                           0.7904         1.1850
     8.3 Lasso(alpha = 1)                                           1.0001         1.9251
     8.4 SVR(kernel = 'rbf', gamma='scale', C=1.0, epsilon=0.1)     1.0001         1.9251
     8.5 KNeighborsRegressor(n_neighbors= 2 )                       1.8478         6.5294
     8.6 DecisionTreeRegressor(random_state = 0)                    0.8586         1.6569

## 9. ผลลัพธ์ของโมเดลการคาดการณ์ COD ใหม่จากชุดข้อมูลคุณภาพน้ำของแม่น้ำนักดงในเดือนมิถุนายนถึงสิงหาคมระหว่างปี 2017 - 2020

     |                             MODEL                                                                                                             |     MAE      |     MSE     |   R-Squared     
     9.1 LinearRegression(fit_intercept = False, n_jobs = None, positive = False)                                                                         0.7987         1.2175        0.8079
     9.2 Ridge(alpha = 10.0, fit_intercept = False, random_state = None)                                                                                  0.7788         1.1566        0.8175
     9.3 Lasso(alpha = 0.01, fit_intercept = False, random_state = None)                                                                                  0.7812         1.1606        0.8168
     9.4 SVR(C = 10, degree = 3, epsilon = 0.01, gamma = 'auto')                                                                                          1.7267         5.7188        0.0977
     9.5 KNeighborsRegressor(algorithm = 'auto', n_neighbors = 7, p= 1, weights= 'distance')                                                              1.5473         4.7114        0.2566
     9.6 DecisionTreeRegressor(max_depth = None, min_samples_leaf = 4,min_samples_split = 4, random_state = None, splitter = 'random')                    0.8598         1.4201        0.7759

     
