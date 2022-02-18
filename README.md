# Entrega_Individual_Algoritmos

Ejercicio 8: Porcentajes, IVA e inversiones.


Ejercicio 9: Media aritmética ponderada

Entrada
  n1,n2,n3: REAL    # Tres números dados
  k: ENTERO         # La cantidad de números, en este caso 3
Resultado: REAL     # La media aritmética de dichos 

Realización
   #Cálculo de la media de números
   m = (n1 + n2 + n3) / 3

Poscondición
   #Cálculo de la media ponderada y sus coeficientes
   c1, c2, c3: REAL  # Coeficientes de ponderación
 Resultado: REAL     # La media ponderada de los números
 
 Precondición
   c1 + c2 + c3 = 1
 Realización
    #Cálculo de la media ponderada
    m= c1 x n1 + c2 x n2 + c3 x n3
   
   
Ejercicio 10: Área de un triángulo.

#Área de un triángulo
Entrada
   h: REAL  # Altura relativa del triángulo
   l: REAL  # Medida de un lado del triángulo
Resultado: REAL

Precondición
   h,l > 0
Realización
   Resultado = (b x h) / 2

#Para el triángulo rectángulo se seguiría el mismo procedimiento ya que sus catetos son perpendiculares y pueden conformar la base y la altura.

Ejercicio 11: Salario y horas extras.


Ejercicio 12: Cuenta de depósito.

#Importe en cuenta
Entrada
   saldo: RACIONAL  #Cantidad de dinero en el banco
   descubierto: RACIONAL  #Cantidad de dinero no suficiente para afrontar un pago
Invariante:
   decubierto = 0
   descubierto ≤ saldo
Precondición
   saldo_inicial ≥ 0
Postcondición 
   c.descubierto = 0 #El descubierto no está autorizado
