<img alt="UCU" src="https://www.ucu.edu.uy/plantillas/images/logo_ucu.svg"
width="150"/>

# Universidad Católica del Uruguay

## Facultad de Ingeniería y Tecnologías

### Programación II

# Desafío Git #1: Calculadora Colaborativa

## Objetivo

Crear una aplicación de calculadora simple en C# donde cada estudiante del
equipo contribuya con una operación diferente (suma, resta, multiplicación,
división). Los estudiantes practicarán los siguientes comandos de Git:
[clone](https://git-scm.com/docs/git-clone),
[checkout](https://git-scm.com/docs/git-checkout),
[pull](https://git-scm.com/docs/git-pull),
[add](https://git-scm.com/docs/git-add),
[commit](https://git-scm.com/docs/git-commit),
[stash](https://git-scm.com/docs/git-stash),
[merge](https://git-scm.com/docs/git-merge) y
[push](https://git-scm.com/docs/git-push).

> [!NOTE]
> El código provisto inicialmente en este repositorio no compila; los
> cambios que harás con tu equipo durante esta actividad lograrán que compile y
> funcione.

## Pasos

### 1. Crear un repositorio a partir de esta plantilla

  Para trabajar en un proyecto en Git debes tener un repositorio. Puedes crear
  localmente un repositorio y luego subirlo a un servidor para que tus
  compañeros lo usen, o puedes clonar un repositorio compartido en un servidor;
  en este ejercicio usaremos esta última opción, clonando este repositorio
  plantilla a tu propio repositorio.

- En este paso, todos los estudiantes leen todas estas instrucciones primero,
  luego <font color="red">**sólo uno**</font> de ellos las ejecuta.
- <font color="red">**Uno**</font> de los estudiantes hace clic en el botón `Use
  this template` que aparece arriba a la derecha en esta página; luego hace clic
  en la opción `Create a new repository`.
- En el cuadro de texto `Repository name`, ese estudiante escribe un nombre para
  el repositorio -puede usar el que quiera, incluso el que le sugiere GitHub,
  mientras sea único en la organización-; no cambien ninguna otra opción.
- Verán en el navegador el nuevo repositorio, con este mismo contenido.
  Compartan en el equipo el link al repositorio. Continúen con los pasos a
  continuación.

### 2. Clonar el repositorio

  > [!TIP]
  > Te recomendamos que elijas una carpeta -o que crees una nueva- para
  > todos los repositorios del curso. Recuerda cómo llegar a esa capeta desde la
  > línea de comandos -puedes volver consultar [este
  > documento](https://github.com/ucudal/PII_Comandos/blob/master/Consola.md) si
  > fuera necesario-.

- **<font color="red">Cada</font>** estudiante abre una terminal y se ubica en
  la carpeta que eligieron para tener todos sus repositorios.
- Luego clona el repositorio en su máquina local con [git
  clone](https://git-scm.com/docs/git-clone), ejecutando el siguiente comando en
  la terminal:

  ```bash
  git clone <url-del-repositorio>
  ```

  > La `<url-del-repositorio>` es la dirección que aparece en el navegador luego
  > del último de los pasos anteriores.

  Git muestra mensajes similares a estos; en lugar de `<nombre-repositorio>`
  aparecerá el nombre que eligieron al crear el repositorio en el paso 1:

  ```bash
  Cloning into '<nombre-repositorio>'...
  remote: Enumerating objects: 9, done.
  remote: Counting objects: 100% (9/9), done.
  remote: Compressing objects: 100% (8/8), done.
  remote: Total 9 (delta 0), reused 4 (delta 0), pack-reused 0
  Receiving objects: 100% (9/9), 9.54 KiB | 4.77 MiB/s, done.
  ```

  El comando `git clone` crea una copia local del repositorio en la URL indicada
  en una carpeta cuyo nombre coincide con el nombre del repositorio. Para
  moverte a esa carpeta, usa el siguiente comando:

  ```bash
  cd <nombre-repositorio>
  ```

  > El nombre del repositorio es el que hayan elegido en el paso [1. Crear un repositorio a partir de esta plantilla](#1-crear-un-repositorio-a-partir-de-esta-plantilla). Pueden ver
  > todas las carpetas en el directorio actual con los comandos `ls` en
  > ![macOS](https://img.shields.io/badge/macOS-000000?style=flat&logo=apple&logoColor=white)
  > y
  > ![linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
  > o `dir` en
  > ![windows](https://custom-icon-badges.demolab.com/badge/Windows-0078D6?logo=windows11&logoColor=white).

### 3. Crear ramas para cada uno

- Cada estudiante crea su propia rama para la operación que va a implementar con
  [git checkout](https://git-scm.com/docs/git-checkout), ejecutando el
  siguiente comando en la terminal:

  ```bash
  git checkout -b <nombre-rama>
  ```

  > El <nombre-rama> corresponde a la operación que cada estudiante va a
  > implementar; es uno de los siguientes:
  > - suma
  > - resta
  > - multiplica
  > - divide

  Git muestra un mensaje similar al siguiente:

  ```bash
  Switched to a new branch '<nombre-rama>'
  ```

### 4. Implementar la operación

- Cada estudiante abre el repositorio en Rider con el siguiente comando:

  ```bash
  rider .
  ```

  > Noten que hay un punto, separado por un espacio, al final del comando.

  Rider les pedirá que confirmen si quieren abrir el proyecto en esa carpeta;
  elijan la opción `Open`. Eventualmente, Rider también les preguntará si es
  seguro abrir el proyecto; elijan la opción `Trust and Open`.

- Cada estudiante implementa su respectiva operación en una nueva clase en C#,
  agregando el código que aparece a continuación <font color="red">**al
  final**</font> del archivo `Program.cs` que está en la carpeta `src` del
  proyecto.

  > Estarás agregando nuevas clases en un mismo archivo `Program.cs`; en el
  > futuro, cada clase se agregará en su propio archivo `.cs` -cuyo nombre
  > coincidirá con el de la clase-, pero para este ejercicio todos agregarán sus
  > clases en el mismo archivo. No te preocupes si no entiendes del todo el
  > código que estás usando, el objetivo es que experimentes cómo es el
  > desarrollo colaborativo -entre varios estudiantes- y concurrente -al mismo
  > tiempo- en Git.

  Estudiante A (suma):

  ```csharp
  public class Addition
  {
     public static int Add(int a, int b)
     {
         return a + b;
     }
  }
  ```

  Estudiante B (resta):

  ```csharp
  public class Substraction
  {
     public static int Substract(int a, int b)
     {
         return a - b;
     }
  }
  ```

  Estudiante C (multiplicación):

  ```csharp
  public class Multiplication
  {
     public static int Multiply(int a, int b)
     {
         return a * b;
     }
  }
  ```

  Estudiante D (división):

  ```csharp
  public class Division
  {
     public static double Divide(int a, int b)
     {
         return (double)a / b;
     }
  }
  ```

### 5. Agregar y hacer *commit* de los cambios

> En lugar de "hacer *commit*" a veces decimos "comitear". El verbo "comitear"
> no existe, pero los desarrolladores lo usamos igual y entre nosotros nos
> entendemos 😀.

- Después de implementar sus operaciones, todos los estudiantes agregan y hacen
  *commit* de sus cambios con [git add](https://git-scm.com/docs/git-add) y [git
  commit](https://git-scm.com/docs/git-commit), ejecutando los siguientes
  comandos en la terminal; noten que hay un punto, precedido de un espacio, al
  final del comando `git add`:

  ```bash
  git add .
  git commit -m "Implementación de la operación <nombre de la operación>"
  ```

  > Puedes ejecutar estos comandos en la terminal que venías usando. Rider
  > incluye también una terminal a la que puedes acceder con el comando `View |
  > Tool Windows | Terminal` o mediante el ícono
  > ![](https://intellij-icons.jetbrains.design/icons/TerminalIcons/icons/expui/toolwindow/terminal@20x20.svg)
  > que aparece abajo a la izquierda. De forma predeterminada, la terminal del
  > Rider se abre en la carpeta raíz del proyecto que tienes abierto.

### 6. Guardar temporalmente los cambios

Vamos a suponer que mientras estás realizando cambios en el repositorio, sin
haber finalizado tu trabajo, debes hacer modificaciones sin perder los cambios
que has hecho hasta el momento —es decir, tienen que poder volver a
recuperarlos—; como los cambios son temporales, tampoco quieres hacer *commit*.

- Cada estudiante agrega la siguiente línea de comentario inmediatamente antes
  del código que agregaron en el paso anterior:

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

- Guarda estos cambios temporalmente con [git
  stash](https://git-scm.com/docs/git-stash), sin hacer *commit*, para poder
  realizar otras modificaciones.

  ```bash
  git stash
  ```

  El código vuelva a quedar como estaba luego de ejecutar el comando `git
  commit` en el paso 5. Puede ser necesario cerrar y volver a abrir el archivo
  `Program.cs` para ver reflejados los cambios en Rider.

- Ejecuta el siguiente comando para volver al código que tenías al comienzo de
  este paso:

  ```bash
  git stash pop
  ```

  Nuevamente, puede ser necesario cerrar y volver a abrir el archivo
  `Program.cs` para ver reflejados los cambios en Rider.

Git muestra un mensaje similar al siguiente:

```text
On branch '<nombre-rama>'
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   src/Program/Program.cs

```

Resolveremos esto a continuación.

### 7. Enviar los cambios al repositorio remoto

Hasta ahora estuvieron trabajando en la copia local del repositorio, es
necesario enviar los cambios al repositorio que está en el servidor.

- Cada estudiante agrega y hace *commit* de los últimos cambios —el comentario
  que agregaron en el paso anterior-:

  ```bash
  git add .
  git commit -m "Comentario agregado"
  ```

  > Noten que hay un espacio, seguido de un punto, al final del comando `git
  > add`.

- Cada estudiante envía sus cambios al repositorio remoto con [git
  push](https://git-scm.com/docs/git-push), ejecutando el siguiente comando en
  la terminal:

  ```bash
  git push origin <nombre-rama>
  ```

  > El `<nombre-rama>` es el que usaron antes; uno de los siguientes:
  > - suma
  > - resta
  > - multiplica
  > - divide

  Deberías ver varios mensajes, similares, aunque no necesariamente iguales, a
  los siguientes:

  ```bash
  Enumerating objects: 14, done.
  Counting objects: 100% (14/14), done.
  Delta compression using up to 8 threads
  Compressing objects: 100% (8/8), done.
  Writing objects: 100% (10/10), 931 bytes | 931.00 KiB/s, done.
  Total 10 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
  ...
  ```

### 8. Obtener cambios y hacer *merge*

> En lugar de "hacer merge" a veces decimos "mergear". El verbo mergear tampoco
> existe, pero al igual que sucede con comitear, los desarrolladores lo usamos y
> nos entendemos entre nosotros 😀.

Ahora llegó el momento de hacer *merge* —combinar— los cambios en las ramas de
trabajo con la rama principal. Antes de hacer *merge* de sus cambios, deben
obtener los cambios de los compañeros. Dependiendo del orden en el que hagan el
trabajo, puede haber conflictos, que deberán resolver.

- Antes de hacer *merge* de sus ramas, cada estudiante debe obtener los últimos
  cambios de la rama `main`. Usa [git
  checkout](https://git-scm.com/docs/git-checkout) para cambiar la rama actual a
  `main`; ejecuta los siguientes comandos en la terminal:

  ```bash
  git checkout main
  ```

  - Luego, <font color="red">**de a un estudiante a la vez**</font>, obtengan
    los últimos cambios con [git pull](https://git-scm.com/docs/git-pull) y
    luego "mergeen" esos cambios en la rama `main` con los de su propia rama,
    ejecutando los siguientes comandos:

    ```bash
    git pull
    git merge <nombre-rama>
    git push
    ```

  > El `<nombre-rama>` es el que usaron antes; uno de los siguientes:
  > - suma
  > - resta
  > - multiplica
  > - divide

    En caso de que no haya conflictos, aparecerá un texto como el que mostramos
    a continuación:

    ```text
    Updating bdd7c4d..fb5eaa0
    Fast-forward
    src/Program/Program.cs | 9 +++++++++
    1 file changed, 9 insertions(+)
    ```

    En caso de que haya conflictos, verán un mensaje como el siguiente:

    ```text
    Auto-merging src/Program/Program.cs
    CONFLICT (content): Merge conflict in src/Program/Program.cs
    Automatic merge failed; fix conflicts and then commit the result.
    ```

    El código en `Program.cs` luce similar al que aparece a continuación, con
    unos marcadores `<<<<<<<`, `=======`, y `>>>>>>>`:

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

    Lo que está entre `<<<<<<<` y `=======` es lo que está en conflicto en la
    rama actual `main`; lo que está entre `=======` y `>>>>>>>` es lo que está
    en conflicto en la rama que están "mergeando". Git no puede resolver el
    conflicto, deben hacerlo ustedes.

    En este caso, ambas modificaciones deben quedar en el archivo, por lo tanto,
    basta borrar los marcadores. En otros casos, la resolución del conflicto
    será diferente. En cualquier caso, el código final no debe incluir los
    marcadores. Puedes ver cómo debe quedar el código completo al final de esta
    página.

    Para terminar, hagan *commit* y *push* de los cambios:

    ```bash
    git add .
    git commit -m "Resolución de conflictos"
    git push
    ```

## Ejemplo final de código

Después de hacer *merge* de todas las contribuciones de los miembros del equipo,
el programa debería verse más o menos así:

```csharp
Console.WriteLine(Addition.Add(7, 2));
Console.WriteLine(Substraction.Substract(10, 1));
Console.WriteLine(Multiplication.Multiply(3, 3));
Console.WriteLine(Division.Divide(18, 2));

public class Addition
{
    public static int Add(int a, int b)
    {
        return a + b;
    }
}

public class Substraction
{
    public static int Substract(int a, int b)
    {
        return a - b;
    }
}

public class Multiplication
{
    public static int Multiply(int a, int b)
    {
        return a * b;
    }
}

public class Division
{
    public static double Divide(int a, int b)
    {
        return (double)a / b;
    }
}
```
