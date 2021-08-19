# [Description](https://colab.research.google.com/drive/1XHQn6se_dY0RzCw83KHU66OKzl2B1Wux#scrollTo=Projeto_Ci_ncia_de_Dados_Previs_o_de_Vendas)

The challange in this case is to built a model predict the monthly sale of a company based on his spending in advertising on TV, Radio and Newspaper.

# [Data Analysis](https://colab.research.google.com/drive/1XHQn6se_dY0RzCw83KHU66OKzl2B1Wux#scrollTo=An_lise_Explorat_ria)
![correlation](https://user-images.githubusercontent.com/83030060/130148073-303eb866-0c34-4488-b42a-171ec5a5479b.jpg)
![pairplot](https://user-images.githubusercontent.com/83030060/130148109-6aa9c4ca-58e4-4c5d-92a6-a5a464b0d735.jpg)

# [Machine Learning Model](https://colab.research.google.com/drive/1XHQn6se_dY0RzCw83KHU66OKzl2B1Wux#scrollTo=Escolhendo_o_Modelo)
In this case I opted to use the RandomForestRegressor to reach the expeted results.

~~~python
print("Accuracy score of {}: {:.2f}%".format(modelo_random_forest, metrics.r2_score(y_test, previsao_rf)*100))
~~~
Accuracy score of RandomForestRegressor: 96.75%

## Prediction View
~~~python
aux = pd.DataFrame()
aux["Y_test"] = y_test
aux["Random Forest"] = previsao_rf

sns.lineplot(data=aux)
~~~
![predict_graphic](https://user-images.githubusercontent.com/83030060/130148451-4f686a3b-ea72-42e0-8327-69ff49692ffa.jpg)

## Feature Importances
~~~python
sns.barplot(x = x_test.columns, y = modelo_random_forest.feature_importances_)
~~~
![feature_importances](https://user-images.githubusercontent.com/83030060/130148592-ea99d2cf-dd7a-4d13-86f4-5fda62919205.jpg)
