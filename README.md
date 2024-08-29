# Ciclos y arreglos 4
Codigo 2 de ciclos y arreglos en python

    def calcular_BMI(peso, estatura):
        bmi = peso / estatura ** 2
        return bmi

    def clasificacion(bmi):
        if bmi < 18.5:
        return "bajo peso"
    elif 18.5 <= bmi <= 24.9:
        return "peso normal"
    elif 25 <= bmi <= 29.9:
        return "sobrepeso"
    else:
        return "obesidad"

    def calcular_Pi(bmi_objetivo, estatura):
        peso_ideal = bmi_objetivo * estatura ** 2
        return peso_ideal

    def imprimir_peso_ideal(categoria, peso, estatura):
        if categoria == "bajo peso":
            peso_ideal = calcular_Pi(18.5, estatura)
            print(f"Para alcanzar un bmi de 18.5, el peso ideal es {peso_ideal:.2f} kg.")
        elif categoria == "sobrepeso":
            peso_ideal = calcular_Pi(24.9, estatura)
            print(f"Para alcanzar un bmi de 24.9, el peso ideal es {peso_ideal:.2f} kg.")
        elif categoria == "obesidad":
            peso_ideal = calcular_Pi(24.9, estatura) 
            print(f"Para alcanzar un bmi de 24.9, el peso ideal es {peso_ideal:.2f} kg.")

    bajo_peso = 0
    peso_normal = 0
    sobrepeso = 0
    obesidad = 0

    personas = int(input("Digite el número de personas: "))

    for i in range(personas):
        print(f"Persona {i + 1}:")
        peso = float(input("Digite el peso de la persona en kg: "))
        estatura = float(input("Digite la estatura en metros de la persona: "))
    
    bmi = calcular_BMI(peso, estatura)
    print(f"El IMC de la persona {i + 1} es igual a {bmi:.2f}")
    
    categoria = clasificacion(bmi)
    print(f"Categoría: {categoria}")
    
    if categoria == "bajo peso":
        bajo_peso += 1
        imprimir_peso_ideal(categoria, peso, estatura)

    elif categoria == "peso normal":
        peso_normal += 1

    elif categoria == "sobrepeso":
        sobrepeso += 1
        imprimir_peso_ideal(categoria, peso, estatura)

    elif categoria == "obesidad":
        obesidad += 1
        imprimir_peso_ideal(categoria, peso, estatura)

    if personas > 0:
        porcentaje_b = (bajo_peso / personas) * 100
        porcentaje_n = (peso_normal / personas) * 100
        porcentaje_s = (sobrepeso / personas) * 100
        porcentaje_o = (obesidad / personas) * 100
    
        print(f"El porcentaje de personas en bajo peso es: {porcentaje_b:.2f}%")
        print(f"El porcentaje de personas en peso normal es: {porcentaje_n:.2f}%")
        print(f"El porcentaje de personas en sobrepeso es: {porcentaje_s:.2f}%")
        print(f"El porcentaje de personas en obesidad es: {porcentaje_o:.2f}%")
