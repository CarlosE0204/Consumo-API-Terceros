# Descripción del proyecto
En este trabajo se realizó un componente login el cual valida usuarios y contraseñas, esto lo hace consumiendo una API de usuarios de la cual se recuperan sus correos y sus contraseñas.
Una vez que se hace la validación de que el usuario exista dentro de la API y que es correcto se envía a una página de principal en la cual el usuarios tendrá la vista del programa.
El proyecto se desarrolló utilizando el framework Angular en su version 18.2.11 y se utilizaron componentes de material para hacer el login y el home.

## Servicio para conectar con la API
Ene este ejercicio se realizó la consulta con la API utilizando un servicio e implementado en protocolo HttpClient con el cual se mantendrá la comunicación entre el proyecto y la API a  la que se está realizando la consulta. Para comunicarnos con la API se necesita la URL que se meustra en la imagen y esto nos devuelve un Observable el cual se utilizará mas tarde en el proyecto.
![image](https://github.com/user-attachments/assets/b6e716c7-85a9-4308-893d-f9f776c041ac)

## Componente Login
### ngOnInit()
Este método es el que se ejecuta una vez en la página web cuando se carga por primera vez o se refresca, ya que en este método se hace un llamado al observable que nos devuelve el servicio con el que se consultó a la API. Se espera que lo que nos devulva la consulta de la API sea un arreglo de usuarios es por ello que se declaró con anterioridad en el archivo .ts esta variable y es a esta misma en donde se guardan todos los datos del consumo de la API.
![image](https://github.com/user-attachments/assets/afb86148-9636-41a5-9f4e-90ca26a7826a)

### validar()
En este método validar se realiza la comprobación de que los campos del correo y de la contraseña tengran datos ingresados para que al momento deque intenete el usuario iniciar sesión, se notifique si algun campo no fue ingresado o en su defecto que revise que al menos contengan alguna dato, en caso de que no haya datos, o falte algun campo se mostrará un mensaje de error en donde especifique que campo está vacío.
![image](https://github.com/user-attachments/assets/befcaa99-5deb-4bf3-b258-40faee65d704)

### ingresar()
Para este método primero se realiza la validación de los campos y en caso de que si hayan datos ingresados se declara una constante en la cual se recibe un booleano, ya que se busca en todo el arreglo de usuarios con la funcion find para verificar que si existe un usuario con el correo y la contraseña asignada. Despues de realizar la busqueda se verifica si se encontró un usuario y contraseña con los mismos datos ingresados, de ser así se muestra la página del home, de no ser así se muestra un nuevo mensaje de error que no se encontró el usuario.
Para este trabajo no se utilizó el auth que es una manera mucho más segura de autenticar los usuarios, esto debido a que el API que se utilizó solo nos otorga el permiso get, siendo que post es el permiso que se necesita para la autenticación.
![image](https://github.com/user-attachments/assets/3d2c1a63-67ac-4a5a-9485-9ef961e571cd)

## Ejecución
![image](https://github.com/user-attachments/assets/4f91defe-829a-4480-93d8-636a038dd403)

Cuando el usuario y contraseña ingresados son correctos nos envía a la página del home.
![image](https://github.com/user-attachments/assets/d765dcc1-dff6-44ff-9fba-cd6331491715)

### Con error
En caso de que el usuario no ingrese el correo se mostrará de esta manera.
![image](https://github.com/user-attachments/assets/4a4bd750-66c4-44b1-a4fb-d5a6a1d23834)

En caso de que el usuario no ingrese la contraseña se mostrará de esta forma.
![image](https://github.com/user-attachments/assets/755e4ebb-9601-41ab-a570-787c86ecd23b)

Finalmente si no ingresa ningun datos se mostraran ambos errores.
![image](https://github.com/user-attachments/assets/7f509f57-ce17-4d2e-ac02-4cfb79c7aa55)

### Usuario no encontrado 
En este caso el usuario con el correo administrador@gmail.com no esxite por lo tanto nos muestra el mensaje de esta manera.
![image](https://github.com/user-attachments/assets/53612611-540f-4477-8d43-63b12c554dc5)



## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.
