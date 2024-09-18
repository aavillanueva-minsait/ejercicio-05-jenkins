import java.text.SimpleDateFormat
import java.time.temporal.ChronoUnit
Date fechaNacimiento = new SimpleDateFormat("dd-MM-yyyy").parse("20-12-1994")
rutaFichero = "C:\\fechaNacimiento.txt"

pipeline
{
    agent any
    stages
    {
        stage("Realizar suma")
        {
            steps
            {
                script
                {
                    actualYear = new SimpleDateFormat("yyyy").parse(new Date())
                    yearsCalculated = Integer.parseInt(actualYear) - fechaNacimiento.getYear()
                    resultado = "Tu edad actual es: " + yearsCalculated
                    println(resultado)
                }
            }
        }
        stage("Guardar Resultado")
        {
            steps
            {
                script
                {
                    writeFile(file: rutaFichero, text: resultado)
                    println("El resultado está listo en: " + rutaFichero)
                }
            }
        }
    }
}
