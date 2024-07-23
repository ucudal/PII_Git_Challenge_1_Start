<img alt="UCU" src="https://www.ucu.edu.uy/plantillas/images/logo_ucu.svg" width="150"/>

### Universidad Católica del Uruguay
## Facultad de Ingeniería y Tecnologías
## Programación II


# Desafío Git #1: Calculadora Colaborativa

## Objetivo
Crear una aplicación de calculadora simple en C# donde cada estudiante del equipo contribuya con una operación diferente (suma, resta, multiplicación, división). Los estudiantes practicarán los siguientes comandos de Git: [clone](https://git-scm.com/docs/git-clone), [checkout](https://git-scm.com/docs/git-checkout), [pull](https://git-scm.com/docs/git-pull), [add](https://git-scm.com/docs/git-add), [commit](https://git-scm.com/docs/git-commit), [stash](https://git-scm.com/docs/git-stash) y [push](https://git-scm.com/docs/git-push).

### Pasos

1. **Configurar el Repositorio**
   - Un estudiante (Estudiante A) inicializa un repositorio Git en una plataforma como GitHub o GitLab y agrega la estructura base del proyecto de la calculadora.

   ```bash
   git init
   git add .
   git commit -m "Commit inicial con estructura base del proyecto"
   git remote add origin <url-del-repositorio>
   git push -u origin master
   ```

2. **Clonar el Repositorio**
   - Todos los estudiantes clonan el repositorio en sus máquinas locales.

   ```bash
   git clone <url-del-repositorio>
   ```

3. **Crear Ramas de Características**
   - Cada estudiante crea su propia rama para la característica que va a implementar.

   ```bash
   git checkout -b feature-addition
   git checkout -b feature-subtraction
   git checkout -b feature-multiplication
   git checkout -b feature-division
   ```

4. **Implementar Características**
   - Cada estudiante implementa su respectiva operación en una nueva clase en C#.

   ```csharp
   // Estudiante A (Suma)
   public class Suma
   {
       public static int Sumar(int a, int b)
       {
           return a + b;
       }
   }

   // Estudiante B (Resta)
   public class Resta
   {
       public static int Restar(int a, int b)
       {
           return a - b;
       }
   }

   // Estudiante C (Multiplicación)
   public class Multiplicacion
   {
       public static int Multiplicar(int a, int b)
       {
           return a * b;
       }
   }

   // Estudiante D (División)
   public class Division
   {
       public static double Dividir(int a, int b)
       {
           return (double)a / b;
       }
   }
   ```

5. **Añadir y Commit Changes**
   - Después de implementar sus características, los estudiantes añaden y comitean sus cambios.

   ```bash
   git add .
   git commit -m "Implementar característica de suma"
   git commit -m "Implementar característica de resta"
   git commit -m "Implementar característica de multiplicación"
   git commit -m "Implementar característica de división"
   ```

6. **Guardar Cambios (Opcional)**
   - Si un estudiante necesita cambiar de rama y tiene cambios sin comitear, puede guardar sus cambios.

   ```bash
   git stash
   ```

7. **Enviar Cambios**
   - Los estudiantes envían sus cambios al repositorio remoto.

   ```bash
   git push origin feature-addition
   git push origin feature-subtraction
   git push origin feature-multiplication
   git push origin feature-division
   ```

8. **Obtener Cambios**
   - Antes de fusionar sus ramas, los estudiantes deben obtener los últimos cambios de la rama master para asegurarse de que no haya conflictos.

   ```bash
   git checkout master
   git pull origin master
   ```

9. **Crear Pull Requests**
   - Los estudiantes crean pull requests para que sus características sean revisadas y fusionadas en la rama master.

10. **Revisar y Fusionar**
    - El propietario del repositorio revisa los pull requests y los fusiona en la rama master.

### Ejemplo Final de Código
Después de fusionar todas las características, el programa principal podría verse así:

```csharp
using System;

namespace CalculadoraColaborativa
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Suma: " + Suma.Sumar(5, 3));
            Console.WriteLine("Resta: " + Resta.Restar(5, 3));
            Console.WriteLine("Multiplicación: " + Multiplicacion.Multiplicar(5, 3));
            Console.WriteLine("División: " + Division.Dividir(5, 3));
        }
    }

    public class Suma
    {
        public static int Sumar(int a, int b)
        {
            return a + b;
        }
    }

    public class Resta
    {
        public static int Restar(int a, int b)
        {
            return a - b;
        }
    }

    public class Multiplicacion
    {
        public static int Multiplicar(int a, int b)
        {
            return a * b;
        }
    }

    public class Division
    {
        public static double Dividir(int a, int b)
        {
            return (double)a / b;
        }
    }
}
```

### Notas
- Asegúrate de que todos los estudiantes tengan Git y un entorno de desarrollo C# configurado.
- Fomenta la comunicación y colaboración durante el ejercicio.
- Aborda cualquier conflicto que surja durante las fusiones como una oportunidad de aprendizaje.