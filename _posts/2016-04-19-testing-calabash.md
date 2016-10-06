---
layout: post
title: Testing automático de aplicaciones Android 
meta: 
description: Tutorial my básico en el que explico como instalar y configurar Calabash para realizar testeos automaticos de aplicaciones Android. 
category:
emote: DxAbomb
---

***

Calabash es un framework open source que permite el testing automatizado de aplicaciones moviles desarrollado por Xamarin; para ello utiliza Cucumber, software escrito en Ruby pensado para el testing de software, aunque es independiente del lenguaje utilizado.

Calabash ejecuta una serie de pruebas funcionales automatizadas contra la interfaz de usuario de una aplicación. Está pensado para ser usado en un modelo de Testing BDD.

<h5>Instalación y funcionamiento</h5>

Para empezar a instalarlo, tienes que tener instalado Ruby, si no lo tienes lo puedes instalar desde aquí: <a href="http://RubyInstaller.org">RubyInstaller.org</a>

También, tienes que tener instalado el JDK (Java Development Kit), que lo puedes descargar de <a href="http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html">aqui </a>y el SDK de Android, lo puedes descargar desde <a href="http://developer.android.com/intl/es/sdk/">aqui</a>

Una vez instalado todo esto tienes que ejecutar el siguiente comando para instalarlo:
<ul>
 	<li><em><strong><code>gem install calabash-android</code></strong></em></li>
</ul>
Si ya has instalado calabash, puedes generar un esqueleto Cucumber con el siguiente comando:
<ul>
 	<li><em><strong><code>calabash-android gen</code></strong></em></li>
</ul>
Automáticamente generará las carpetas con los archivos .feature y .rb

En el archivo con extension .feature se especifica lo que queremos que ejecute automáticamente. Por ejemplo un feature con un escenario para el login muy sencillo, de una aplicación quedaría de esta manera:
   
   ```python
    Feature: Login Feature
    Scenario: As a valid user I can log into my app
    Given I enter text "luisca_jl" into field with id "txtLogin" //pasamos los id de los elementos como string
    And I enter "1234" into input field number 2
    And I go back //Vuelve atras para cerrar el teclado
    When I press "btnLogin"
    Then I see "Bienvenido de nuevo" 
   ```
  
Puedes ejecutar el testing en la maquina virtual de Android que viene con el SDK o directamenete en nuestro dispositivo si esta conectado a nuestro ordenador.

Por último ejecutamos el comando para que empiece automáticamente a testear la aplicación:
<ul>
 	<li><em><strong><code>calabash-android run &lt;apk&amp;gt</code></strong></em></li>
</ul>
Y automáticamente abrirá la aplicación en la maquina virtual o en nuestro dispositivo si lo tenemos conectado.

<img class="responsive-img" src="http://i1.wp.com/frostq.ml/wp-content/uploads/2016/04/Animation.gif">