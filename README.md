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


