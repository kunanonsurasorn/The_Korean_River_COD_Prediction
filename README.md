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

     |                             MODEL                                                                                                             |     MAE      |     MSE     |   R-Squared   |   
     9.1 LinearRegression(fit_intercept = False, n_jobs = None, positive = False)                                                                         0.7987         1.2175        0.8079
     9.2 Ridge(alpha = 10.0, fit_intercept = False, random_state = None)                                                                                  0.7788         1.1566        0.8175
     9.3 Lasso(alpha = 0.01, fit_intercept = False, random_state = None)                                                                                  0.7812         1.1606        0.8168
     9.4 SVR(C = 10, degree = 3, epsilon = 0.01, gamma = 'auto')                                                                                          1.7267         5.7188        0.0977
     9.5 KNeighborsRegressor(algorithm = 'auto', n_neighbors = 7, p= 1, weights= 'distance')                                                              1.5473         4.7114        0.2566
     9.6 DecisionTreeRegressor(max_depth = None, min_samples_leaf = 4,min_samples_split = 4, random_state = None, splitter = 'random')                    0.8598         1.4201        0.7759

## 10. ผลลัพธ์ของโมเดลการคาดการณ์ COD จากชุดข้อมูลคุณภาพน้ำของแม่น้ำยองซันในเดือนมิถุนายนถึงสิงหาคมของปี 2020

     |                             MODEL                                                                                                             |     MAE      |     MSE     |     
     10.1 LinearRegression(fit_intercept = False, n_jobs = None, positive = False)                                                                        1.1237         6.6095    
     10.2 Ridge(alpha = 10.0, fit_intercept = False, random_state = None)                                                                                 1.0395         4.5149
     10.3 Lasso(alpha = 0.01, fit_intercept = False, random_state = None)                                                                                 1.0515         4.8160
     10.4 SVR(C = 10, degree = 3, epsilon = 0.01, gamma = 'auto')                                                                                         2.5100        11.4438
     10.5 KNeighborsRegressor(algorithm = 'auto', n_neighbors = 7, p= 1, weights= 'distance')                                                             2.5191        13.0675
     10.6 DecisionTreeRegressor(max_depth = None, min_samples_leaf = 4, min_samples_split = 4, random_state = None, splitter = 'random')                  1.2556         4.0798

## 11. ผลลัพธ์ของโมเดลการคาดการณ์ COD จากชุดข้อมูลคุณภาพน้ำของแม่น้ำยองซันในเดือนมิถุนายนถึงสิงหาคมของปี 2020

     |                             MODEL                                                                                                             |     MAE      |     MSE     |     
     11.1 LinearRegression(fit_intercept = False, n_jobs = None, positive = False)                                                                        0.9347         1.8513    
     11.2 Ridge(alpha = 10.0, fit_intercept = False, random_state = None)                                                                                 0.9398         1.7709
     11.3 Lasso(alpha = 0.01, fit_intercept = False, random_state = None)                                                                                 0.9388         1.7764
     11.4 SVR(C = 10, degree = 3, epsilon = 0.01, gamma = 'auto')                                                                                         2.5352         8.6404
     11.5 KNeighborsRegressor(algorithm = 'auto', n_neighbors = 7, p= 1, weights= 'distance')                                                             2.0270         6.4447
     11.6 DecisionTreeRegressor(max_depth = None, min_samples_leaf = 4, min_samples_split = 4, random_state = None, splitter = 'random')                  1.1730         2.9024

## 12. ผลลัพธ์ของโมเดลการคาดการณ์ COD จากชุดข้อมูลคุณภาพน้ำของแม่น้ำกึมในเดือนมิถุนายนถึงสิงหาคมของปี 2020

     |                             MODEL                                                                                                             |     MAE      |     MSE     |     
     12.1 LinearRegression(fit_intercept = False, n_jobs = None, positive = False)                                                                        2.0113         9.9762    
     12.2 Ridge(alpha = 10.0, fit_intercept = False, random_state = None)                                                                                 1.9444         9.8418
     12.3 Lasso(alpha = 0.01, fit_intercept = False, random_state = None)                                                                                 1.9692         10.1276
     12.4 SVR(C = 10, degree = 3, epsilon = 0.01, gamma = 'auto')                                                                                         2.4173         11.1578
     12.5 KNeighborsRegressor(algorithm = 'auto', n_neighbors = 7, p= 1, weights= 'distance')                                                             2.6398         13.3086
     12.6 DecisionTreeRegressor(max_depth = None, min_samples_leaf = 4, min_samples_split = 4, random_state = None, splitter = 'random')                  1.8585         6.9622

## 13. ผลลัพธ์ของโมเดลการคาดการณ์ COD จากชุดข้อมูลคุณภาพน้ำของแม่น้ำนักดง แม่น้ำยองซัม แม่น้ำฮัน และแม่น้ำกึมในเดือนมิถุนายนถึงสิงหาคมระหว่างปี 2017 - 2020

     |                             MODEL                                                                                                             |     MAE      |     MSE     |   R-Squared   |     
     13.1 LinearRegression(fit_intercept = False, n_jobs = None, positive = False)                                                                        0.9307         1.9189         0.8274    
     13.2 Ridge(alpha = 10.0, fit_intercept = False, random_state = None)                                                                                 0.9290         1.8957         0.8295
     13.3 Lasso(alpha = 0.01, fit_intercept = False, random_state = None)                                                                                 0.9323         1.8846         0.8305
     13.4 SVR(C = 10, degree = 3, epsilon = 0.01, gamma = 'auto')                                                                                         2.3902        10.5852         0.0480
     13.5 KNeighborsRegressor(algorithm = 'auto', n_neighbors = 7, p= 1, weights= 'distance')                                                             1.8474         7.1883         0.3535
     13.6 DecisionTreeRegressor(max_depth = None, min_samples_leaf = 4, min_samples_split = 4, random_state = None, splitter = 'random')                  1.0753         2.4318         0.7812

## 14. ผลลัพธ์ของโมเดลการคาดการณ์ COD จากชุดข้อมูลคุณภาพน้ำของแม่น้ำนักดง แม่น้ำยองซัม แม่น้ำฮัน และแม่น้ำกึมในเดือนมิถุนายนถึงสิงหาคมระหว่างปี 2017 - 2020 โดยพิจารณาจากพารามิเตอร์ที่เหมาะสมจากชุดคำสั่ง Script ค้นหาโมเดลที่เหมาะสมจากการประเมินด้วย Mean Absolute Error ของ Linear Regression, Ridge Linear Regression, Lasso Linear Regression และ Decision Tree Regressor ซึ่งในกรณีนี้จะไม่พิจารณา SVR และ KNeighborsRegressor

models3 = [
    {'name': 'Linear Regression',
      'model': LinearRegression(),
      'param_grid': {'fit_intercept': [True,False],
                            'n_jobs': [None,1,5,10],
                            'positive': [True,False]}},
    {'name': 'Ridge Linear Regression',
      'model': Ridge(),
      'param_grid': {'alpha': [0.01, 0.1, 1.0, 10.0],
                           'fit_intercept': [True,False],
                           'random_state': [None,1,42]}},
    {'name': 'Lasso Linear Regression',
      'model': Lasso(),
      'param_grid': {'alpha': [0.01, 0.1, 1.0, 10.0],
                           'fit_intercept': [True,False],
                           'random_state': [None,1,42]}},
    {'name': 'Decision Tree Regressor',
      'model': DecisionTreeRegressor(),
      'param_grid': {'max_depth': [None, 4],
                           'splitter': ['best','random'],
                           'min_samples_split': [2,3,4],
                           'min_samples_leaf': [2,3,4],
                           'random_state': [None,1,42]
                          }}
    ]

results3 = []

for model_info3 in models3:
    model3 = model_info3['model']
    param_grid3 = model_info3['param_grid']
    grid_search3 = GridSearchCV(model3, param_grid3,cv= 5,scoring='neg_mean_absolute_error')
    grid_search3.fit(ifdx_train,ifdy_train)

    best_model3 = grid_search3.best_estimator_
    ifdy_pred = best_model3.predict(ifdx_test)
    score_model3 = mean_absolute_error(ifdy_test, ifdy_pred)

    results3.append({
        'Model': model_info3['name'],
        'Best Parameters': grid_search3.best_params_,
        'Mean Absolute Error': score_model3
    })

# Display the results
results3_df = pd.DataFrame(results3)
results3_df

     |                             MODEL                                                                                                             |     MAE      |     MSE     |
     14.1 LinearRegression(fit_intercept = False, n_jobs = None, positive = True)                                                                         0.9392         1.9433         
     14.2 Ridge(alpha = 0.01, fit_intercept = False, random_state = None)                                                                                 0.9307         1.9187         
     14.3 Lasso(alpha = 0.1, fit_intercept = False, random_state = None)                                                                                  0.9393         1.9001        
     14.4 DecisionTreeRegressor(max_depth = None, min_samples_leaf = 4,min_samples_split = 2, random_state = None, splitter = 'random')                   1.1021         2.6579                                                                     
