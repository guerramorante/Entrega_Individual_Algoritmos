# Entrega_Individual_Algoritmos

Ejercicio 8: Porcentajes, IVA e inversiones.

Entrada
precio_sin_impuesto: REAL #Precio sin impuesto
porcentaje_IVA: REAL #Porcentaje de un IVA dado

Resultado
  TII = precio_sin_impuesto x (1 + porcentaje_IVA)

fin cálculo precio

Entrada 
capital_invertido: REAL #Cantidad de dinero invertido
tipo_interés: REAL #Porcentaje de ganancias por tiempo determinado
tiempo: ENTERO #Tiempo transcurrido (en meses)

Resultado
   tipo_interes x tiempo/30 x capital principal

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
    m = c1 x n1 + c2 x n2 + c3 x n3
   
   
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
#Salario_bruto
#Horas_mensuales

Entrada
   salario_mensual_bruto: REAL #Importe de salario mensual en bruto
   horas_extras: ENTERO #Cantidad de horas extras a pagar

precondición
   salario_mensual_bruto > 0
   horas_extras ≥ 0
Invariante
   cantidad_semanas: ENTERO #Cantidad de semanas de trabajo en este caso 52
   cantidad_horas_semanales: ENTERO #Cantidad legal de horas de trabajo en este caso 35
   cantidad_horas_max_1: ENTERO #Umbral de cambio de precio de remuneración en este caso 8
   precio_1: REAL #Tarifa de remuneración cantidad_horas_max_1 primeras horas extras en este caso 1,25
   precio_2: REAL #Tarifa de remuneración de las otras horas extras en este caso 1,5
Variable
   horas_extra_1: ENTERO #Cantidad de horas extra con precio_1
   horas_extra_2: ENTERO #Cantidad de horas extra con precio_2
   precio_hora: REAL #Precio hora de la remunerción bruta básica
Realización
   Calcular el precio_hora de la remuneración bruta básica
Resultado 
   precio_hora x (inf(horas_extra, cantidad_horas_max_1) x precio_1 + sup(horas_extra - cantidad_max_1, 0) x precio_2)

fin horas_extra
#Cálculo de la cantidad de horas de cada categoría
horas_extra_1 = inf(horas_extra, cantidad_horas_max_1)
horas_extra_2 = sup(horas_extra - cantidad_horas_max_1, 0)
#Cálculo de la remuneración de las horas extra
Resultado
   precio_hora x (horas_extra_1 x precio_1 + horas_extra_2 x precio_2)

fin cálculo horas_extras

#Cálculo precio hora bruto
precio_hora_bruto(salario_mensual_bruto: REAL) #Precio bruto correspondiente al salario_mensual_bruto

Precondición
    salario_mensual_bruto > 0

Invariante
    cantidad_semanas: ENTERO #Cantidad de semanas de trabajo, 52 en este caso
    cantidad_horas_semanas: ENTERO #Cantidad de horas semanales de trabajo legales, 35 en este caso

#Cálculo del precio_hora de la remunerarión bruta base
Resultado
   salario_mensual_bruto x 12 / (real(cantidad_horas_semana) x real(cantidad_semanas))
Postcondición
  Resultado = salario_mensual_bruto x 12,0 / real(35 x 52)

fin precio_hora_bruto


Ejercicio 12: Cuenta de depósito.

#Importe en cuenta
Entrada
   saldo: RACIONAL  #Cantidad de dinero en el banco
   descubierto: RACIONAL  #Cantidad de dinero no suficiente para afrontar un pago
   retirada_dinero: RACIONAL #Cantidad de dinero a extraer de la cuenta
   ingreso_dinero: RACIONAL #Cantidad de dinero a ingresar en la cuenta
Invariante:
   decubierto = 0
   descubierto ≤ saldo
Precondición
   saldo_inicial ≥ 0
Postcondición 
   c.descubierto = 0 #El descubierto no está autorizado
Resultado
   saldo_inicial - retirada_dinero ≥ 0 #Ya que el descubierto es igual a 0
   saldo_inicial + ingreso_dinero > 0
fin CUENTA
Entrada
   saldo: RACIONAL  #Cantidad de dinero en el banco
   descubierto: RACIONAL  #Cantidad de dinero no suficiente para afrontar un pago
   retirada_dinero: RACIONAL #Cantidad de dinero a extraer de la cuenta
   ingreso_dinero: RACIONAL #Cantidad de dinero a ingresar en la cuenta
Precondición
   saldo_inicial > 0
   descubierto_MAX ≥ 0
Poscondición
   c.descubierto = descubierto_MAX
   c.saldo = saldo_inicial
fin CUENTA
Entrada
   Tipo_de_cuenta
    saldo: REAL 
    descubierto: REAL # Importe del descubierto autorizado
    fecha_descubierto: FECHA # Fecha de inicio del último descubierto
    duración_MAX: FECHA # Duración máxima del descubierto
    invariante
        # El descubierto está autorizado durante un tiempo limitado
        descubierto ≥ 0
        fecha_descubierto ≠ 0
        fecha_descubierto + duración_max ≤ fecha_actual
        # El saldo debe der superior al descubierto autorizado
        saldo ≥ descubierto
fin CUENTA
