<img alt="UCU" src="https://www.ucu.edu.uy/plantillas/images/logo_ucu.svg" width="150"/>

### Universidad Católica del Uruguay
## Facultad de Ingeniería y Tecnologías
## Programación II


# Desafío Git #1: Calculadora Colaborativa

## Objetivo
Crear una aplicación de calculadora simple en C# donde cada estudiante del equipo contribuya con una operación diferente (suma, resta, multiplicación, división). Los estudiantes practicarán los siguientes comandos de Git: [clone](https://git-scm.com/docs/git-clone), [checkout](https://git-scm.com/docs/git-checkout), [pull](https://git-scm.com/docs/git-pull), [add](https://git-scm.com/docs/git-add), [commit](https://git-scm.com/docs/git-commit), [stash](https://git-scm.com/docs/git-stash) y [push](https://git-scm.com/docs/git-push).

## Pasos

1. **Crear un repositorio a partir de esta plantilla**

> Para trabajar en un proyecto en Git debes tener un repositorio. Puedes crear localmente un repositorio y luego subirlo a un servidor para que tus compañeros lo usen, o puedes clonar un repositorio compartido en un servidor; en este ejercicio usaremos esta última opción, clonando este repositorio plantilla a tu propio repositorio.

- Todos los estudiantes leen todas estas instrucciones primero, luego <font color="red">**sólo uno**</font> de ellos las ejecuta.
- <font color="red">**Uno**</font> de los estudiantes hace clic en el botón `Use this template` que aparece arriba a la derecha en esta página; luego hace clic en la opción `Create a new repository`.
- En el cuadro de texto `Repository name`, ese estudiante escribe un nombre para el repositorio -puede usar el que quiera, incluso el que te sugiere GitHub, mientras sea único en la organización-; no cambia ninguna otra opción.
- Verá en su navegador el nuevo repositorio, con este mismo contenido; continúen con los pasos a continuación.

2. **Clonar el Repositorio**

> Te recomendamos que elijas una carpeta -o que crees una nueva- para todos los repositorios del curso. Recuerda cómo llegar a esa capeta desde la línea de comandos -puedes volver consultar [este documento](https://github.com/ucudal/PII_Comandos/blob/master/Consola.md) si fuera necesario-.

- **<font color="red">Cada</font>** estudiante abre una terminal y se ubica en la carpeta que eligieron para tener todos sus repositorios.
- Luego clona el repositorio en su máquina local con el siguiente comando:
    
  ```bash
  git clone <url-del-repositorio>
  ```

  > La \<url-del-repositorio\> es la dirección que aparece en el navegador luego del último de los pasos anteriores.

3. **Crear ramas para cada uno**

- Cada estudiante crea su propia rama para la operación que va a implementar con el siguiente comando:

  ```bash
  git checkout -b <nombre-rama>
  ```

  > El <nombre-rama> corresponde a la operación que cada estudiante va a implementar; es uno de los siguientes:
  > - feature-addition
  > - feature-subtraction
  > - feature-multiplication
  > - feature-division

  El comando `git checkout` crea una copia local del repositorio indicado en una carpeta cuyo nombre coincide con el del repositorio. Para moverte a esa carpeta, usa el siguiente comando:

  ```bash
  cd <nombre-repositorio>
  ```

  > El <nombre-repositorio> es el que hayan elegido en el paso 1. Puedes ver todas las carpetas en el directorio actual con los comandos `ls` ![macOS](https://img.shields.io/badge/macOS-000000?style=flat&logo=apple&logoColor=white) y ![linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black) o `dir` ![windows](https://img.shields.io/badge/Windows-0078D6?style=flat&logo=windows&logoColor=white).

4. **Implementar la operación**

- Cada estudiante abre el repositorio en Rider con el siguiente comando:

  ```bash
  rider .
  ```

  > Noten que hay un punto, separado por un espacio, al final del comando.

  Rider les pedirá que confirmen si quieren abrir el proyecto en esa carpeta; elijan la opción `Open`. Eventualmente, Rider también les preguntará si es seguro abrir el proyecto; elijan la opción `Trust and Open`.

- Cada estudiante implementa su respectiva operación en una nueva clase en C#, agregando el código que aparece a continuación <font color="red">**al final**</font> del archivo `Program.cs` que está en la carpeta `src` del proyecto.

  > Estarás agregando nuevas clases en un mismo archivo `Program.cs`; en el futuro, cada clase se agregará en su propio archivo `.cs` -cuyo nombre coincidirá con el de la clase-, pero para este ejercicio todos agregarán sus clases en el mismo archivo. No te preocupes si no entiendes del todo el código que estás usando, el objetivo es que experimentes cómo es el desarrollo colaborativo -entre varios estudiantes- y concurrente -al mismo tiempo- en Git.

  Estudiante A (suma):
  ```csharp
  public class Suma
  {
     public static int Sumar(int a, int b)
     {
         return a + b;
     }
  }
  ```
  
  Estudiante B (resta):
  ```csharp
  public class Resta
  {
     public static int Restar(int a, int b)
     {
         return a - b;
     }
  }
  ```
  
  Estudiante C (multiplicación):
  ```csharp
  public class Multiplicacion
  {
     public static int Multiplicar(int a, int b)
     {
         return a * b;
     }
  }
  ```
  
  Estudiante D (división):
  ```csharp
  public class Division
  {
     public static double Dividir(int a, int b)
     {
         return (double)a / b;
     }
  }
  ```

5. **Agregar y "comitear" los cambios**

> El verbo `comitear` no existe, pero los desarrolladores lo usamos igual y entre nosotros nos entendemos 😀.

- Después de implementar sus operaciones, los estudiantes agregan y comitean sus cambios con los siguientes comandos:

  ```bash
  git add .
  git commit -m "Implementación de la operación <nombre de la operación>"
  ```
  
  > Puedes ejecutar estos comandos en la terminal que venías usando. Rider incluye también una terminal a la que puedes acceder con el comando `View | Tool Windows | Terminal` o mediante el ícono ![](https://intellij-icons.jetbrains.design/icons/TerminalIcons/icons/expui/toolwindow/terminal@20x20.svg) que aparece abajo a la izquierda.

6. **Guardar temporalmente los cambios**

Vamos a suponer que mientras estás realizando cambios en el repositorio, sin haber finalizado tu trabajo, debes hacer modificaciones sin perder los cambios que has hecho hasta el momento —es decir, tienen que poder volver a recuperarlos—; como los cambios son temporales, tampoco quieres "comitearlos".

- Cada estudiante agrega la siguiente línea de comentario inmediatamente antes del código que agregaron en el paso anterior:

    ```csharp
    // Esta clase implementa la operación <nombre-operación>
    ```

    > Reemplaza <nombre-operación> según corresponda
    
    Por ejemplo, para la operación de la resta, el código debería quedar así:
    
    ```csharp
    // Esta clase implementa la operación resta
    public class Resta
    {
        public static int Restar(int a, int b)
        {
            return a - b;
        }
    }
    ```

- Guarda estos cambios temporalmente, sin "comitearlos", para poder realizar otras modificaciones.

  ```bash
  git stash
  ```
  
  El código vuelva a quedar como estaba luego de ejecutar el comando `git commit` en el paso 5.


- Ejecuta el siguiente comando para volver al código que tenías al comienzo de este paso:

  ```bash
  git stash pop
  ```

7. **Enviar los cambios**

Hasta ahora estuvieron trabajando en la copia local del repositorio, es necesario enviar los cambios al repositorio que está en el servidor.

- Cada estudiante agrega y "comitea" los últimos cambios —el comentario que agregaron en el paso anterior-:

  ```bash
  git add .
  git commit -m "Comentario agregado"
  ```

  > Noten que hay un espacio, seguido de un punto, al final del comando `add`.

- Cada estudiante envía sus cambios al repositorio remoto.

  ```bash
  git push origin <nombre-rama>
  ```

  > El <nombre-rama> es el que usaron antes; uno de los siguientes:
  > - feature-addition
  > - feature-subtraction
  > - feature-multiplication
  > - feature-division

  Deberías ver varios mensajes, similares, aunque no necesariamente iguales, a los siguientes:

  ```bash
  Enumerating objects: 14, done.
  Counting objects: 100% (14/14), done.
  Delta compression using up to 8 threads
  Compressing objects: 100% (8/8), done.
  Writing objects: 100% (10/10), 931 bytes | 931.00 KiB/s, done.
  Total 10 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
  ...
  ```

8. **Obtener cambios y "mergear"**

> El verbo mergear tampoco existe, pero al igual que sucede con comitear, los desarrolladores lo usamos y nos entendemos entre nosotros 😀.

Ahora llegó el momento de "mergear" —combinar— los cambios en las ramas de trabajo con la rama principal. Antes de "mergear" sus cambios deben obtener los cambios de los compañeros. Dependiendo del orden en el que hagan el trabajo, puede haber conflictos, que deberán resolver.

- Antes de "mergear" sus ramas, cada estudiante debe obtener los últimos cambios de la rama `main`.

  ```bash
  git checkout master
  git pull
  ```
  
  - Luego "mergea" los cambios de su rama con los de la rama `main`, ejecutando el siguiente comando:

    ```bash
    git merge <nombre-rama>
    git push
    ```
  
  >   El <nombre-rama> es el que usaron antes; uno de los siguientes:
  >   - feature-addition
  >   - feature-subtraction
  >   - feature-multiplication
  >   - feature-division

    En caso de que haya conflictos, verán un mensaje como el siguiente:
  
    ```bash
    Auto-merging src/Program/Program.cs
    CONFLICT (content): Merge conflict in src/Program/Program.cs
    Automatic merge failed; fix conflicts and then commit the result.
    ```
  
    El código en `Program.cs` luce similar al que aparece a continuación, con unos marcadores `<<<<<<<`, `=======`, y `>>>>>>>`:
  
    ```csharp
    namespace Ucu.Poo.GitChallenge;
  
    public static class Program
    {
      public static void Main()
      {
      Console.WriteLine(Suma.Sumar(1, 2));
      Console.WriteLine(Resta.Restar(3, 4));
      Console.WriteLine(Multiplicacion.Multiplicar(5, 6));
      Console.WriteLine(Division.Dividir(7, 8));
      }
    }
    <<<<<<< HEAD
    ⋯
    =======
    ⋯
    >>>>>>>
    ```
  
    Lo que está entre `<<<<<<<` y `=======` es lo que está en conflicto en la rama actual `main`; lo que está entre `=======` y `>>>>>>>` es lo que está en conflicto en la rama que están "mergeando". Git no puede resolver el conflicto, deben hacerlo ustedes.
  
    En este caso, ambas modificaciones deben quedar en el archivo, por lo tanto, basta borrar los marcadores. En otros casos, la resolución del conflicto será diferente. En cualquier caso, el código final no debe incluir los marcadores.
  
    Para terminar, "comiteen" y "pusheen" los cambios:
  
    ```bash
    git commit -m "Resolución de conflictos"
    git push
    ```

## Ejemplo Final de Código

Después de "mergear" todas las contribuciones de los miembros del equipo, el programa debería verse más o menos así:

```csharp
namespace Ucu.Poo.GitChallenge;

public static class Program
{
    public static void Main()
    {
        Console.WriteLine(Suma.Sumar(1, 2));
        Console.WriteLine(Resta.Restar(3, 4));
        Console.WriteLine(Multiplicacion.Multiplicar(5, 6));
        Console.WriteLine(Division.Dividir(7, 8));
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
```
