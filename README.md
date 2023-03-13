# PRACTICA HTML Y CSS

Para la práctica, he decidido hacer una página web sobre venta de entradas de un grupo (BTS). 
En la página principal he puesto un menú horizontal y un menú vertical. Y de entrada una galeria de imágenes de los integrantes de este grupo.
En el menú horizontal tenemos los horarios (tabla de los escenarios con las canciones), el formulario que se debe de hacer para poder comprar una entrada. Y los precios, en el que se ve una galeria de fotos más grande y con el precio marcado debajo. 

Codigo de la pagina principal.
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <link rel="stylesheet" type="text/css" href="ventaDeEntradas/menu.css">


    <style>
        body {
            background-image: url('fondomoradoo.jpg');
        }


        header {
            padding: 30px;
            text-align: center;
            font-size: 2em;
            color: rgb(0, 0, 0);
            transition: color 0.5s ease-in-out;
        }

        header:hover {
            color: rgb(241, 144, 220);

        }


        /* menu */




        ul.menu {

            position: fixed;
            background: #a468a7;
            border: 1px solid #030202;
            list-style: none;
            margin: 0;
            padding: 0;
            width: 100%;
            top: 0;
            left: 0;
            font-size: 1em;

            box-sizing: border-box;
            z-index: 999;

        }

        ul.menu:hover {
            border: 1px solid #883bec;
        }


        ul.menu li {
            float: left;
            width: 25%;
            position: relative;

        }

        /* poner ancho de la primera "casilla" */

        ul.menu li a {
            color: #ffffff;
            display: block;
            padding: .3em;
            text-decoration: none;
            font-family: Georgia, 'Times New Roman', Times, serif;

        }

        /* cambiamos color de la letra */



        ul.menu ul {
            display: none;
            position: absolute;
            top: 100%;
            left: 0;
            padding: 0;
            margin: 0;
            border: 1px solid #a562b3;
            background-color: #a562b3;
            width: 100%;
        }




        /* cambiar el bloque de opciones */


        ul.menu li:hover>ul {
            display: block;

        }

        /* para que aparezcan las opciones */

        ul.menu ul li {
            float: none;
            width: 100%;

        }

        /* para que no aparezcan seguidas */

        ul.menu ul li a {
            color: #ffffff;
            padding: .3em;
            display: block;
        }

        ul.menu ul li:hover>a {
            background-color: #a472aa;


            position: relative;
            animation-name: formulario;
            animation-duration: 5s;


        }





        @keyframes formulario {
            0% {
                background-color: rgb(116, 16, 111);
            }

            50% {
                background-color: #b264b4;
            }

            100% {
                background-color: rgb(116, 16, 111);
            }
        }

        /* menu final */


        /* inicio galeria imagenes */




        .imagenesga {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            grid-gap: 10px;
        }

        .gallery {
            background-color: #68b4f1a8;
            padding: 10px;
        }

        div.gallery {
            border: 1px solid #ccc;
        }

        div.gallery:hover {
            border: 1px solid #883bec;
        }

        div.gallery img {
            width: 100%;
            height: 300px;
            object-fit: cover;
        }

        div.desc {
            padding: 15px;
            text-align: center;
        }

        * {
            box-sizing: border-box;
        }

        .responsive {
            padding: 0 6px;
            float: left;
            width: 100%;
        }

        @media only screen and (max-width: 700px) {
            .responsive {
                width: 50%;
                margin: 6px 0;
            }
        }

        @media only screen and (max-width: 500px) {
            .responsive {
                width: 100%;
            }
        }

        .clearfix:after {
            content: "";
            display: table;
            clear: both;
        }



        /* final galeria imagenes */

        /* inicio menu lateral */
        .menuuulat {
            display: flex;
            flex-direction: row;

        }

        .menuuu {
            height: 100%;
            width: 200px;
            background-color: #a562b3;
            color: #fff;
            padding: 20px;
            box-sizing: border-box;
            transform: translateX(0);
            transition: transform 0.3s ease-in-out;
        }

        .menuuu h2 {
            margin: 0 0 10px 0;
        }

        .menuuu ul {
            list-style: none;
            margin: 0;
            padding: 0;
        }

        .menuuu ul li a {
            display: block;
            padding: 10px;
            color: #fff;
            text-decoration: none;
        }

        .main-content {
            flex-grow: 5;
            padding: 20px;
        }

        #botonmenuuu {
            display: none;
        }

        #botonmenuuu:checked~.menuuu {
            transform: translateX(0);
        }

        .toggle-btn {
            display: none;
        }

        @media (max-width: 9000px) {
            .menuuu {
                width: 20%;
                height: auto;
                position: absolute;
                top: 70px;
                left: 0;
                transform: translateX(-100%);
            }

            #botonmenuuu:checked~.menuuu {
                transform: translateX(0);
            }

            .toggle-btn {
                display: block;
                font-size: 1.5em;
                cursor: pointer;
                position: absolute;
                top: 30px;
                left: 20px;
            }



        }

        /* final menu lateral */


        @media (max-width: 600px) {

            .menuuu ul {
                font-size: 0.5em;
            }

            .menuuu h2 {
                font-size: 0.9em;
            }
        }

        footer {
            padding: 10px;
            text-align: center;
            color: black;
            transition: color 0.5s ease-in-out;
        }

        footer:hover {
            color: rgb(241, 144, 220);

        }
    </style>
</head>

<body>




    <nav>
        <ul class="menu">
            <li><a href="#">ENTRADAS</a>
                <ul>
                    <li><a href="horario.html">HORARIO</a></li>
                    <li><a href="ejercicio12.formulario.html">FORMULARIO</a></li>
                </ul>
            </li>
            <li><a href="precios.html">PRECIOS</a></li>
        </ul>
    </nav>

    <header>
        <h2>BTS venta de entradas</h2>
    </header>

    <div class="menuuulat">
        <input type="checkbox" id="botonmenuuu">
        <div class="menuuu">
            <h2>Mas información</h2>
            <nav>
                <ul>
                    <li><a href="#">Lugar:</a></li>
                    <li><a href="#">España</a></li>
                    <li><a href="#">Contacto:</a></li>
                    <li><a href="#">687517515</a></li>
                </ul>
            </nav>
        </div>
        <label for="botonmenuuu" class="toggle-btn">&#9776;</label>

    </div>

    <div class="imagenesga">



        <div class="responsive">
            <div class="gallery">
                <img src="tae.jpeg" alt="V">
                </a>


            </div>
        </div>


        <div class="responsive">
            <div class="gallery">
                <img src="kook.jpeg" alt="Kook">
                </a>

            </div>
        </div>



        <div class="responsive">
            <div class="gallery">
                <img src="jjhope.jpg" alt="hope">
                </a>

            </div>
        </div>



        <div class="responsive">
            <div class="gallery">
                <img src="suga.jpeg" alt="suga">
                </a>

            </div>
        </div>



        <div class="responsive">
            <div class="gallery">
                <img src="rm.jpeg" alt="rm">
                </a>

            </div>
        </div>

        <div class="responsive">
            <div class="gallery">
                <img src="jmin.jpg" alt="jimin">
                </a>

            </div>
        </div>



        <div class="responsive">
            <div class="gallery">
                <img src="jin.jpeg" alt="jin">
                </a>

            </div>
        </div>




    </div>

    <footer>
        <p>BTS</p>
    </footer>


</body>

</html>


Codigo del horario.

<!DOCTYPE html>

<html>

<head>
    <title>Horario</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <link rel="icon" type="image/x-icon" href="calendar_date_event_schedule_icon_127191.ico">
    <style>
        header {
            padding: 15px;
            text-align: center;
            font-size: 2em;
            color: black;
            transition: color 0.5s ease-in-out;
        }

        header:hover {
            color: rgb(241, 144, 220);

        }


        body {
            background-image: url('btsfondo2.jpg');

        }


        table,
        th,
        td {
            border: 1px solid rgb(0, 0, 0);
            padding: 15px;
            border-radius: 5px;
        }

        th,
        td {
            text-align: center;
        }

        th,
        td {
            padding: 15px;
        }


        .dies {
            background-color: #AACAF9;
        }



        article {
            float: left;
            padding: 15px;
            width: 100%;
            height: 300px;


        }

        section::after {
            content: "";
            display: table;
            clear: both;
            height: 300PX;
        }

        footer {
            padding: 10px;
            text-align: center;
            color: black;
            transition: color 0.5s ease-in-out;
        }

        footer:hover {
            color: rgb(241, 144, 220);

        }

        table tr:nth-child(even) {
            background-color: #e67af5;
        }

        table tr:nth-child(odd) {
            background-color: pink;
        }
    </style>
</head>

<body>

    <header>
        <h2>Horario</h2>
    </header>

    <section>
        <article>
            <table class="tabla" style="width:100%">


                <colgroup>
                    <col span="1" style="background-color: pink">

                </colgroup>

                <tr>
                    <th>HORA</th>
                    <th class="dies">Escenario 1</th>
                    <th class="dies">Escenario 2</th>
                    <th class="dies">Escenario 3</th>
                    <th class="dies">Escenario 4</th>
                    <th class="dies">Escenario 5</th>

                </tr>
                <tr>
                    <td>18:00</td>
                    <td>Blue and Grey</td>
                    <td>Boy with Luv</td>
                    <td>Butter</td>
                    <td>DNA</td>
                    <td>Euphoria</td>

                </tr>

                </tr>
                <tr>
                    <td>19:00</td>
                    <td>Fake Love</td>
                    <td>I Need U</td>
                    <td>Idol</td>
                    <td>Make It Right</td>
                    <td>Mic Drop</td>




                </tr>
                <tr>
                    <td>20:00</td>
                    <td>Not Today</td>
                    <td>Life Goes On</td>
                    <td>On</td>
                    <td>Run</td>
                    <td>Home</td>



                </tr>

                <tr>
                    <td>21:00</td>
                    <td>Yet to come</td>
                    <td>Save Me</td>
                    <td>Film Out</td>
                    <td>Fire</td>
                    <td>My Universe</td>


                </tr>

                <tr>
                    <td>22:00</td>
                    <td>Lights</td>
                    <td>Airplane</td>
                    <td>A Brand New Day</td>
                    <td>All Night</td>
                    <td>Black Swan</td>


                </tr>

                <tr>
                    <td>23:00</td>
                    <td>Epipphany</td>
                    <td>Permission to Dance</td>
                    <td>Serendipity</td>
                    <td>Waste It on Me</td>
                    <td>Savage Love</td>


                </tr>

                <tr>
                    <td>00:00</td>
                    <td>Spring Day</td>
                    <td>Bad Decisions</td>
                    <td>Blood Sweat and Tears</td>
                    <td>Dynamite</td>
                    <td>Mikrokosmos</td>
                </tr>
            </table>

        </article>
    </section>

    <footer>
        <p>BTS</p>
    </footer>

</body>

</html>


Codigo del formulario.

<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <style>
        body {
            background-image: url('btsfondo.jpg');
            background-repeat: no-repeat;
            background-attachment: fixed;
            background-size: cover;
        }

        header {
            padding: 20px;
            text-align: center;
            font-size: 2em;
            color: black;
            transition: color 0.5s ease-in-out;
        }

        header:hover {
            color: rgb(241, 144, 220);
          
        }



        input[type=text],
        select {
            width: 100%;
            padding: 5px 4px;
            margin: 8px 0;
            display: inline-block;
            border: 1px solid #ccc;
            border-radius: 9px;

        }



        input[type=email],
        select {
            width: 100%;
            padding: 5px 4px;
            margin: 8px 0;
            display: inline-block;
            border: 1px solid #ccc;
            border-radius: 9px;

        }


        input[type=date],
        select {
            width: 100%;
            padding: 5px 4px;
            margin: 8px 0;
            display: inline-block;
            border: 1px solid #ccc;
            border-radius: 9px;

        }





        input[type=submit] {
            width: 100%;
            background-color: #ca86f7;
            color: white;
            padding: 5px 4px;
            margin: 8px 0;
            border: none;
            border-radius: 9px;
            cursor: pointer;
        }

        input[type=reset] {
            width: 100%;
            background-color: #ca86f7;
            color: white;
            padding: 5px 4px;
            margin: 8px 0;
            border: none;
            border-radius: 9px;
            cursor: pointer;
        }

        input[type=submit]:hover {
            background-color: #d47af8;
        }

        input[type=reset]:hover {
            background-color: #d47af8;
            transition: color 0.5s ease-in-out;
        }

         input[type=reset]:hover {
            color: rgb(204, 10, 162);
          
        }







        div {
            border-radius: 5px;
            background-color: #bd68ee;
            padding: 20px;
            align-content: center;
            width: 50%;
            margin-top: 30%;
            margin-left: 24%;

        }



        footer {
            padding: 10px;
            text-align: center;
            color: black;
        }
    </style>
</head>

<body>

    <header>
        <h2>Formulario</h2>
    </header>

    <section>


        <article>



            <div>
                <form action="Ya se ha enviado">
                    <label for="fname">Nombre</label>
                    <input type="text" id="nam" name="nombre" placeholder="Escribe tu nombre" required>

                    <label for="lname">Apellido</label>
                    <input type="text" id="ape" name="apellido" placeholder="Escribe tu apellido" required>


                    <label for="email">Correo electrónico</label>
                    <input type="email" id="email" name="email" placeholder="nombre232@gmail.com" required>


                    <label for="nacimiento">Fecha de Nacimiento:</label>
                    <input type="date" id="nacimiento" name="nacimiento" required>



                    <label for="pais">País</label>
                    <select id="pais" name="pais">
                        <option value="pais">Bolivia</option>
                        <option value="pais">España</option>
                        <option value="pais">Perú</option>
                        <option value="pais">Alemania</option>
                        <option value="pais">Italia</option>
                        <option value="pais">Brasil</option>


                    </select>

                    <input type="submit" name="enviar" value="Enviar">
                    <input type="reset" name="refrescar" value="Reset">
                </form>
            </div>
        </article>
    </section>

    <footer>
        <p>BTS</p>
    </footer>

</body>

</html>

</html>


Codigo de los precios.

<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <style>
        body {
            background-image: url('fondomoradoo.jpg');
        }


        header {
            padding: 30px;
            text-align: center;
            font-size: 2em;
            color: rgb(0, 0, 0);
            transition: color 0.5s ease-in-out;
        }

        header:hover {
            color: rgb(241, 144, 220);
          
        }





        /* inicio galeria imagenes */

        div.gallery {
            border: 1px solid #ccc;
        }

        div.gallery:hover {
            border: 1px solid #883bec;
        }

        div.gallery img {
            width: 100%;

            height: 400px;

            object-fit: cover;
        }

        div.desc {
            padding: 15px;
            text-align: center;
        }

        * {
            box-sizing: border-box;
        }

        .responsive {
            padding: 0 6px;
            float: left;
            width: 24.99999%;
        }

        @media only screen and (max-width: 700px) {
            .responsive {
                width: 49.99999%;
                margin: 6px 0;
            }
        }

        @media only screen and (max-width: 500px) {
            .responsive {
                width: 100%;
            }
        }

      
        .imagenesgal {

            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;

        }

        footer {
            padding: 10px;
            text-align: center;
            color: black;
            transition: color 0.5s ease-in-out;
        }

        footer:hover {
            color: rgb(241, 144, 220);
          
        }
        
    </style>
</head>

<body>


    <header>
        <h2>Precios</h2>
    </header>


    <div class="imagenesga">



        <div class="responsive">
            <div class="gallery">
                <img src="escenarioo.jpg" alt="concert">
                
                <div class="desc"> Escenario 3: 415135€</div>
            </div>
        </div>


        <div class="responsive">
            <div class="gallery">
                <img src="bts9.png" alt="concert">
                
                <div class="desc"> Escenario 1 y 4: 265464€</div>
            </div>
        </div>



        <div class="responsive">
            <div class="gallery">
                <img src="bts4.png" alt="concert">
                
                <div class="desc"> Escenario 5: 541511€</div>
            </div>
        </div>



        <div class="responsive">
            <div class="gallery">
                <img src="bts6.png" alt="concert">
                
                <div class="desc">Escenario 2: 5416168€</div>
            </div>
        </div>


    </div>


   

    <footer>
        <p>BTS</p>
    </footer>

</body>

</html>





