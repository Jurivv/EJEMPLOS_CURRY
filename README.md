Ejemplos de los códigos de curry 

Ejemplo 1:
```curry
-- Definición de un tipo de dato para representar colores
data Color = Rojo | Verde | Azul

-- El operador '?' permite expresar elecciones no deterministas
elegirColor :: Color
elegirColor = Rojo ? Verde ? Azul

main :: IO ()
main = putStrLn ("El color seleccionado es: " ++ show elegirColor)

```
Ejemplo 2:
```curry
module Main where

-- Representación de un grafo como lista de aristas
edges :: [(Int, Int)]
edges = [(1,2), (2,3), (1,3), (3,4)]

-- Función para encontrar un camino desde 'start' hasta 'end'
path :: Int -> Int -> [Int]
path start end = path' start end []

-- Función auxiliar que evita ciclos mediante la lista de visitados
path' :: Int -> Int -> [Int] -> [Int]
path' start end visited
  | start == end = [end]
  | elem start visited = []
  | otherwise =
      let nexts = [ y | (x,y) <- edges, x == start ]
      in start : concatMap (\n -> path' n end (start:visited)) nexts

main :: IO ()
main = do
  let resultado = path 1 4
  putStrLn ("El camino encontrado es: " ++ show resultado)


```
