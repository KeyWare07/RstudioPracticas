# RstudioPracticas

#=================================================================================================
# EJERCICIO 1 - Clasificación de números positivos o negativos
  resultados <- c()
  set.seed(123)
  for (i in 1:10) {  
    num <- sample(-10:10, 1)
    if (num > 0) {
      resultados <- c(resultados, paste(num, "- positivo"))
    } else if (num < 0) {
      resultados <- c(resultados, paste(num, "- negativo"))
    } else {
      resultados <- c(resultados, paste(num, "- cero"))
    }
  }
  cat("Clasificación de los números:\n")
  cat(resultados, sep = "\n")
  

#=================================================================================================
# EJERCICIO 2 - Cálculo de números pares e impares
  set.seed(123)
  numeros <- sample(1:100, 100, replace = TRUE)
  pares <- sum(numeros %% 2 == 0)
  impares <- sum(numeros %% 2 != 0)
  
  cat("Números generados:", numeros, "\n")
  cat("Total de números pares:", pares, "\n")
  cat("Total de números impares:", impares, "\n")


#=================================================================================================
# EJERCICIO 3 - Suma de los primeros N números
  #N <- as.numeric(readline(prompt = "Introduce un número N: "))
  N <- 5
  if (is.na(N)) {
    cat("Por favor, introduce un número válido.\n")
  } else {
    suma <- sum(1:N)
    cat("La suma de los números del 1 al", N, "es:", suma, "\n")
  }


#=================================================================================================
# EJERCICIO 4 - Números de Fibonacci (20)
  a <- 0
  b <- 1
  fibonacci <- c(a, b)
  
  while (length(fibonacci) < 20) {
    siguiente <- a + b
    fibonacci <- c(fibonacci, siguiente)
    a <- b
    b <- siguiente
  }
  
  cat("Los primeros 20 números de la secuencia de Fibonacci son:\n")
  cat(fibonacci, sep = ", ")


#=================================================================================================
# EJERCICIO 5 - Cálculo de factorial
  #n <- as.numeric(readline(prompt = "Introduce un número n para calcular su factorial: "))
  n <- 5
  factorial <- prod(1:n)
  cat("El factorial de", n, "es:", factorial, "\n")

#=================================================================================================
# EJERCICIO 6 - Juego de adivinanza
  set.seed(Sys.time())  
  numero_secreto <- sample(1:100, 1)
  adivinanza <- 0
  
  while (adivinanza != numero_secreto) {
    adivinanza <- as.numeric(readline(prompt = "Adivina el número entre 1 y 100: "))
    
    if (adivinanza < numero_secreto) {
      cat("Es mayor. Intenta de nuevo.\n")
    } else if (adivinanza > numero_secreto) {
      cat("Es menor. Intenta de nuevo.\n")
    } else {
      cat("¡Felicidades! Has adivinado el número:", numero_secreto, "\n")
    }
  }


#=================================================================================================
# EJERCICIO 7 - Validación de contraseña
  contraseña_correcta <- "contraseña"
  intentos <- 0
  max_intentos <- 3
  
  while (intentos < max_intentos) {
    contraseña_ingresada <- readline(prompt = "Introduce la contraseña: ")
    
    if (contraseña_ingresada == contraseña_correcta) {
      cat("Acceso concedido.\n")
      break
    } else {
      intentos <- intentos + 1
      cat("Contraseña incorrecta. Intentos restantes:", max_intentos - intentos, "\n")
    }
  }
  
  if (intentos == max_intentos) {
    cat("Acceso bloqueado.\n")
  }

#=================================================================================================
# EJERCICIO 8 - Suma de dígitos de un número
  #numero <- as.numeric(readline(prompt = "Introduce un número entero: "))
  numero <- 123
  suma <- sum(as.numeric(unlist(strsplit(as.character(abs(numero)), ""))))
  cat("La suma de los dígitos de", numero, "es:", suma, "\n")

#=================================================================================================
# EJERCICIO 9 - Impresión de patrones
  #filas <- as.numeric(readline(prompt = "Introduce un número entero: "))
  filas <- 5
  for (i in 1:filas) {
    cat(rep("*", i), "\n")
  }

#=================================================================================================
# EJERCICIO 10 - Números primos
  cat("Números primos entre 1 y 100:\n")
  for (num in 2:100) {
    es_primo <- TRUE
    for (i in 2:sqrt(num)) {
      if (num %% i == 0) {
        es_primo <- FALSE
        break
      }
    }
    if (es_primo) {
      cat(num, " ")
    }
  }
  cat("\n")

