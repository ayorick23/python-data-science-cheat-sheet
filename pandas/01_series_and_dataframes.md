# Introducción a Series y DataFrames en Pandas

**Pandas** es una de las librerías más utilizadas en Python para la manipulación y análisis de datos. Proporciona estructuras de datos rápidas, flexibles y expresivas diseñadas para trabajar con datos etiquetados (tablas, series temporales, etc.).

## Verificar la versión de Pandas

Antes de comenzar, es buena práctica verificar la versión instalada de `pandas`, especialmente para asegurar la compatibilidad de funciones:

```python
import pandas as pd
print(pd.__version__)
```

## Creación de Series

Una Serie es una estructura unidimensional similar a un array o lista, pero con etiquetas (_índices_).

```python
import pandas as pd

serie = pd.Series([10, 20, 30, 40])
print(serie)
```

Esto crea una serie con índices predeterminados (0, 1, 2, ...).

## Creación de Series con índices personalizados

Puedes definir tus propios índices para mayor control o legibilidad:

```python
serie = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
print(serie)
```

Esto es útil cuando quieres que cada elemento tenga una etiqueta significativa.

## Acceder a valores de una Serie

Puedes acceder a los valores utilizando el índice como si fuera un diccionario o una lista:

```python
print(serie['b'])  # Acceso por etiqueta
print(serie[1])    # Acceso por posición
```

## Creación de DataFrames

Un DataFrame es una estructura bidimensional (_tabla_), similar a una hoja de cálculo o a una tabla SQL.

```python
datos = {
    'Nombre': ['Ana', 'Luis', 'Carlos'],
    'Edad': [23, 34, 45]
}
df = pd.DataFrame(datos)
print(df)
```

## Acceder a columnas del DataFrame

```python
print(df['Nombre'])      # Devuelve una Serie
print(df[['Nombre']])    # Devuelve un DataFrame
```

## Acceder a una fila del DataFrame

### Por índice entero con `iloc[]`

```python
print(df.iloc[1])  # Segunda fila
```

### Por etiqueta con `loc[]`

Si defines un índice personalizado:

```python
df = pd.DataFrame(datos, index=['a', 'b', 'c'])
print(df.loc['b'])  # Fila con índice 'b'
```

## Acceder a celdas específicas

Combinando `loc[]` o `iloc[]` con nombres de columnas:

```python
print(df.loc['b', 'Edad'])     # Edad de 'Luis'
print(df.iloc[1, 1])           # Segunda fila, segunda columna
```
