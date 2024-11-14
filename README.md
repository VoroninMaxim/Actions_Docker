## Настройка GitHub Actions

Использование GitHub Actions для автоматизации задач, 
связанных с записными книжками Jupyter, позволяет значительно 
упростить процесс разработки. Например, можно создать рабочие процессы, 
которые автоматически запускают записные книжки и создают отчеты или 
визуализации при каждой отправке изменений в репозиторий.

```python pip install ...:```
Устанавливает необходимые библиотеки для работы с 
Jupyter Notebook и линтинга/форматирования кода.

```python - name: Run Flake8: ```
Имя шага для запуска линтера Flake8.

```python flake8 --max-line-length=88 --ignore=E203,W503 .: ```
Запускает Flake8 для проверки кода в текущей директории (.). 
Параметры указывают максимальную длину строки и игнорируемые ошибки (E203 и W503).

```python - name: Run Black:```
Имя шага для запуска форматировщика Black.

```python black --check --line-length 88 .:```
Проверяет код на соответствие стандартам форматирования Black 
с максимальной длиной строки 88 символов.

##### Запуск ноутбука и коммит изменений

```python jupyter nbconvert --to notebook --execute credit_default_eda.ipynb```

  Сохраняем результаты выполнения обратно в тот же файл.

```python jupyter nbconvert --to html credit_default_eda.ipynb --output-dir=. --output index.html```
  
Конвертирует выполненный Jupyter Notebook в HTML формат и сохраняет его под именем index.html в текущей директории (.).



[Результаты проверки](https://github.com/VoroninMaxim/Actions_Docker/actions/runs/11827667215)

[Посмотреть отчет](https://voroninmaxim.github.io/Actions_Docker/credit_default_eda.html)