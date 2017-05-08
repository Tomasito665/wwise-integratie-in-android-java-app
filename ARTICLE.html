<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Wwise integratie in Android Java app</title>
<link rel="stylesheet" href="https://stackedit.io/res-min/themes/base.css" />
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>
</head>
<body><div class="container"><h2 id="wwise-integratie-in-android-java-app">Wwise integratie in Android Java app</h2>

<p>Al sinds eind jaren 70 is het gebruikelijk dat games worden voorzien van interactief geluid. Er bestaan verschillende programma’s die deze taak voor de ontwikkelaar vergemakkelijken, waarvan de twee grootste Wwise<a href="#fn:wwise" id="fnref:wwise" title="See footnote" class="footnote">1</a> en FMOD<a href="#fn:fmod" id="fnref:fmod" title="See footnote" class="footnote">2</a>. Deze software wordt voornamelijk gebruikt in games en de tutorials/documentatie zijn alleen daarop gericht. Als je Wwise wilt integreren in een Android app in Java − zonder daar een game-engine voor te gebruiken als Unity of Unreal Engine − blijkt dat nergens is terug te vinden hoe je dat moet doen. Dat is jammer, want er zijn naast games ook ander soort applicaties waar een interactieve audio omgeving als Wwise waardevol kan zijn. Denk aan kunstinstallaties of auditieve feedback bij sport.</p>

<p>De functies van de Wwise SDK<a href="#fn:wwise-sdk" id="fnref:wwise-sdk" title="See footnote" class="footnote">3</a> zijn geschreven in C++. Voor diens integratie in een Android Java app moet er code worden geschreven in zowel Java als C++. De communicatie tussen de twee talen wordt gedaan middels de <em>Java Native Interface</em>, waarmee C/C++ functies kunnen worden aangeroepen vanuit Java. </p>

<p>De C++ code wordt gecompileerd als shared library<a href="#fn:shared-lib" id="fnref:shared-lib" title="See footnote" class="footnote">4</a>. Deze library wordt in Java ingeladen met de <code>System#loadLibrary(String)</code> functie.</p>



<pre class="prettyprint"><code class="language-java hljs "><span class="hljs-comment">// Aan de Java kant</span>
class Foo {
  <span class="hljs-keyword">static</span> {
    System.loadLibrary(<span class="hljs-string">"fooCppLib"</span>);
  }

  <span class="hljs-javadoc">/**
   * Met het "native" sleutelwoord zeg je eigenlijk:
   *
   * Maak je geen zorgen, Java compiler, de implementatie van deze 
   * functie heb ik nu niet bij de hand, maar die krijg je nog van 
   * me tegoed. Je krijgt hem wel pas runtime ;-)
   * 
   * PS: Implementatie zal in binair zijn (aka native) ipv Java 
   *     bytecode.
   */</span>
  <span class="hljs-keyword">native</span> <span class="hljs-keyword">void</span> bar();
}</code></pre>



<pre class="prettyprint"><code class="language-cpp hljs "><span class="hljs-comment">// Aan de C++ kant</span>
<span class="hljs-keyword">extern</span> <span class="hljs-string">"c"</span>
<span class="hljs-keyword">void</span> Java_Foo_bar(JNIEnv* env) { <span class="hljs-comment">/* Implementatie van Foo#bar */</span> }</code></pre>



<h2 id="inhoudsopgave">Inhoudsopgave</h2>

<ul>
<li><a href="#benodigdheden-1">Benodigdheden</a> <br>
<ul><li><a href="#android-studio">Android Studio</a></li>
<li><a href="#android-sdk">Android SDK</a></li>
<li><a href="#android-ndk">Android NDK</a></li>
<li><a href="#wwise">Wwise</a></li></ul></li>
<li><a href="#project-opzetten-1">Project opzetten</a> <br>
<ul><li><a href="#android-manifest">Android Manifest</a></li></ul></li>
<li><a href="#wwise-sdk-importeren">Wwise SDK importeren</a> <br>
<ul><li><a href="#gradle">Gradle</a></li>
<li><a href="#cmake">CMake</a> <br>
<ul><li><a href="#ndk-libraries">NDK Libraries</a></li>
<li><a href="#libzip-headers">Libzip headers</a> <br>
<ul><li><a href="#libzip-configuratie">Libzip configuratie</a></li></ul></li>
<li><a href="#wwise-headers-en-libraries-1">Wwise headers en libraries</a></li></ul></li></ul></li>
<li><a href="#soundengine-io">SoundEngine I/O</a></li>
<li><a href="#wwise-hello-world-soundbank">Wwise Hello-world SoundBank</a> <br>
<ul><li><a href="#soundbank-importeren-in-android-studio-1">Soundbank importeren in Android Studio</a></li></ul></li>
<li><a href="#java-native-interface">Java Native Interface</a> <br>
<ul><li><a href="#java">Java</a></li>
<li><a href="#c">C++</a> <br>
<ul><li><a href="#native-method-implementaties">Native method implementatie’s</a></li></ul></li></ul></li>
<li><a href="#de-app-1">De app</a></li>
</ul>

<h2 id="benodigdheden">Benodigdheden</h2>

<p>Het mixen van Java met andere talen via de JNI is een geavanceerd topic. Solide kennis van Java en C++ is zeer aan te raden.</p>

<h4 id="android-studio">Android Studio</h4>

<p>Android apps zijn te ontwikkelen in Android Studio, IntelliJ IDEA of in Eclipse in combinatie met de ADE<a href="#fn:ade" id="fnref:ade" title="See footnote" class="footnote">5</a> plugin. De officiële manier van ontwikkelen is de eerste. Deze IDE is gemaakt door Google zelf en is te downloaden via <a href="https://developer.android.com/studio/">https://developer.android.com/studio/</a>.</p>



<h4 id="android-sdk">Android SDK</h4>

<p>De Android SDK<a href="#fn:android-sdk" id="fnref:android-sdk" title="See footnote" class="footnote">6</a> bevat libraries om te communiceren met het Android systeem, debugging tools en een Android emulator. De benodigde versie van de Android SDK staat gelijk tot de versie van Android waarvoor je ontwikkelt. In deze tutorial ontwikkelen wij voor Android KitKat (API level 19). De Android SDK is te downloaden vanuit Android Studio, via de SDK Manager.</p>



<h4 id="android-ndk">Android NDK</h4>

<p>Om C/C++ code te compileren voor Android heb je de Android NDK<a href="#fn:android-ndk" id="fnref:android-ndk" title="See footnote" class="footnote">7</a> nodig. Deze is eveneens te downloaden vanuit de Android Studio, via SDK Manager.</p>



<h4 id="wwise">Wwise</h4>

<p>Tijdens de installatie van Wwise is het belangrijk om de <code>SDK (C++)</code> package en het <code>Android</code> deployment platform aan te kruisen. Wwise is te downloaden via <a href="https://www.audiokinetic.com/download/">https://www.audiokinetic.com/download/</a></p>

<p>Maak een <code>WWISE_SDK</code> environment variabele<a href="#fn:env-var" id="fnref:env-var" title="See footnote" class="footnote">8</a> aan en wijs daar het basis pad van de Wwise SDK aan toe. Dit komt later van pas bij het vinden van de Wwise headers en libraries.</p>

<p><strong>Let op</strong> <br>
Om problemen te voorkomen tijdens het compileren is het belangrijk dat het installatie pad van de SDK <strong>geen spatie’s</strong> bevat. Verplaats de SDK zo nodig naar een andere locatie.</p>



<h2 id="project-opzetten">Project opzetten</h2>

<p>Maak een nieuw project aan in Android Studio. Vink daarbij de <strong>C++ support</strong> aan. Zo creëert Android Studio alvast één C++ bronbestand en configureert automatisch de Gradle<a href="#fn:gradle" id="fnref:gradle" title="See footnote" class="footnote">9</a> build voor C++ compilatie. Laat bij de overige configuratie schermen de opties op hun standaardwaardes en klik bij het laatste scherm op <em>Finish</em>.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/ttem0rJLVUCJcYTwPq3RDRQuzmxH1whIdhhb1JGcq3P6k5Xm-zZuNYnSQNghF3lK3m8-ol8m=s231" alt="Android Studio - Welcome screen" title="Android Studio - New Project">&nbsp;&nbsp;<img src="https://lh3.googleusercontent.com/Cmjrf-6y0X5EbpSJzlTTMozL5YvtTKWOYPtMTmASFUEwbyrLGpubrBbj0lkKh3JleV5PDuCc=s362" alt="New Project" title="New project"> <br>
</center> <p></p>

<blockquote>
  <p>Vanaf nu kan je op elk moment de applicatie op je mobiel of op een emulator uitvoeren vanuit Android Studio met deze knop: <img src="https://lh3.googleusercontent.com/-iympYpIlZh0/WQ4Z2VvZzqI/AAAAAAAAJr4/SBKna7eRiHE9fJHCEdX0PMSNRVU8cjrYwCE0/s50/runApp.png" alt="Android studio - Run App" title="Run App"> .</p>
</blockquote>



<h3 id="android-manifest">Android Manifest</h3>

<p>Voeg de volgende machtigingen toe aan het <code>AndroidManifest.xml</code> bestand vóór de <code>&lt;application&gt;</code> tag.</p>

<pre class="prettyprint"><code class=" hljs xml"><span class="hljs-comment">&lt;!-- Nodig voor de communicatie met de Wwise authoring tools --&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-title">uses-permission</span> <span class="hljs-attribute">android:name</span>=<span class="hljs-value">"android.permission.INTERNET"</span> /&gt;</span>

<span class="hljs-comment">&lt;!-- Nodig voor bepaalde geluidseffecten, zoals reverb --&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-title">uses-permission</span> <span class="hljs-attribute">android:name</span>=<span class="hljs-value">"android.permission.MODIFY_AUDIO_SETTINGS"</span> /&gt;</span>

<span class="hljs-comment">&lt;!-- Nodig als je je Soundbanks vanuit de SD kaart wilt lezen --&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-title">uses-permission</span> <span class="hljs-attribute">android:name</span>=<span class="hljs-value">"android.permission.WRITE_EXTERNAL_STORAGE"</span> /&gt;</span>


<span class="hljs-tag">&lt;<span class="hljs-title">application</span>&gt;</span>
    <span class="hljs-comment">&lt;!-- etc --&gt;</span></code></pre>

<h2 id="wwise-sdk-importeren">Wwise SDK importeren</h2>



<h3 id="gradle">Gradle</h3>

<p>Android Studio biedt de mogelijkheid om met Gradle een CMake <a href="#fn:cmake" id="fnref:cmake" title="See footnote" class="footnote">10</a> project toe tevoegen aan het bouwprocess van de app. Omdat je in de tijdens het creëren van het project de <em>C++ Support</em> functie hebt aangevinkt, heeft Android Studio automatisch een CMake project, en dus een <code>CMakeLists.txt</code> bestand aangemaakt en toegevoegd aan het Gradle bouwproces. Dit zie je terug in het <code>build.gradle</code> bestand.</p>



<pre class="prettyprint"><code class="language-gradle hljs bash">apply plugin: <span class="hljs-string">'com.android.application'</span>

android {
    <span class="hljs-comment"># Deze code snippet is niet het het volledige build.gradle bestand. </span>
    <span class="hljs-comment"># Alleen code relevant voor de CMake build wordt hier laten zien.</span>

    defaultConfig {
        externalNativeBuild {
            cmake {
                <span class="hljs-comment"># Ondersteuning voor C++11 (niet vereist voor Wwise)</span>
                cppFlags <span class="hljs-string">"-std=c++11"</span>
            }
        }
    }

    externalNativeBuild {
        cmake {
            path <span class="hljs-string">"CMakeLists.txt"</span>
        }
    }
}</code></pre>

<p>De Wwise SDK libraries voor Android komen in <a href="https://www.audiokinetic.com/library/edge/?source=SDK&amp;id=android__specificinfo.html#android_lib_flavors">vier varianten</a>:</p>

<ul>
<li>armeabi-v7a (met NEON)</li>
<li>x86 (met SSE)</li>
<li>arm64-v8a (met NEON)</li>
<li>x86_64 (met SSE)</li>
</ul>

<p>Voeg in <code>gradle.build</code> de volgende code toe om de compilatie van onze C/C++ code te beperken tot die vier architecturen.</p>

<pre class="prettyprint"><code class="language-gradle hljs bash">android {
    defaultConfig {
        <span class="hljs-comment"># externalNativeBuild { ... }</span>
        ndk {
          abiFilters <span class="hljs-string">"armeabi-v7a"</span>, <span class="hljs-string">"x86"</span>, <span class="hljs-string">"arm64-v8a"</span>, <span class="hljs-string">"x86_64"</span>
        }
    }
    <span class="hljs-comment"># externalNativeBuild { ... }</span>
}</code></pre>

<blockquote>
  <p>Het is aan te raden om tijdens het ontwikkelen de compilatie tot te beperken tot één van die vier architecturen. Anders wordt er bij elke build vier keer gecompileerd.</p>
</blockquote>

<h3 id="cmake">CMake</h3>

<p>Het <code>CMakeLists.txt</code> bestand bevindt zich in <code>${projectDir}/app</code>. Activeer links boven in de <a href="https://www.jetbrains.com/help/idea/2017.1/project-tool-window.html">Project Tool Window</a> de <a href="https://www.jetbrains.com/help/idea/2017.1/project-tool-window.html#d775585e77">Project view</a>. Deze view is gebaseerd op de onderliggende mappen structuur. Dat is handig, omdat we zo een nieuwe map aan gaan maken.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/-ATKEgEZNOfA/WQ7wiqTAqNI/AAAAAAAAJsw/vW0xPgWQA7oFJb1aI7Grmm73oXN66_3mQCE0/s550/Android+Studio+-+Project+View.PNG" alt="Android Studio - Project View" title="View"></center><p></p>

<p>Naast de Gradle configuratie, heeft Android Studio ook het <code>CMakeLists.txt</code> bestand geprepareerd na het aanvinken van de C++ Support. Hier wordt onze <code>native-lib</code> shared library gecompileerd. </p>

<pre class="prettyprint"><code class="language-cmake hljs "><span class="hljs-keyword">cmake_minimum_required</span>(VERSION <span class="hljs-number">3.4</span>.<span class="hljs-number">1</span>)

<span class="hljs-comment"># Creëer een nieuwe shared library, bestaande uit één bronbestand</span>
<span class="hljs-keyword">add_library</span>( native-lib
             SHARED
             src/main/cpp/native-lib.cpp )

<span class="hljs-comment"># Zoek de log library, verschaft door de NDK</span>
<span class="hljs-keyword">find_library</span>( log-lib log )

<span class="hljs-comment"># Link de log library tegen onze native-lib shared library aan</span>
<span class="hljs-keyword">target_link_libraries</span>( native-lib <span class="hljs-envvar">${log-lib}</span> )</code></pre>

<p>Om in ons <code>native-lib.cpp</code> bronbestand gebruik te kunnen maken van de functies uit de Wwise SDK moet het volgende gebeuren.</p>

<ul>
<li>Extra NDK libraries linken</li>
<li>Libzip headers toevoegen</li>
<li>Wwise headers toevoegen</li>
<li>Wwise libraries linken</li>
</ul>



<h4 id="ndk-libraries">NDK Libraries</h4>

<p>Wwise maakt gebruikt van de volgende NDK libraries: libandroid, libz, liblog, libOpenSLES, libEGL en libGLESv1_CM. Voeg deze toe en link ze tegen onze <code>native-lib</code> library aan.</p>



<pre class="prettyprint"><code class="language-cmake hljs "><span class="hljs-keyword">find_library</span> ( android-lib android ) <span class="hljs-comment"># libandroid</span>
<span class="hljs-keyword">find_library</span> ( z-lib z )             <span class="hljs-comment"># libz</span>
<span class="hljs-keyword">find_library</span> ( log-lib log )         <span class="hljs-comment"># liblog</span>
<span class="hljs-keyword">find_library</span> ( opensl-lib OpenSLES ) <span class="hljs-comment"># libOpenSLES</span>
<span class="hljs-keyword">find_library</span> ( egl-lib EGL )         <span class="hljs-comment"># libEGL</span>
<span class="hljs-keyword">find_library</span> ( gles-lib GLESv1_CM )  <span class="hljs-comment"># libGLESv1_CM</span>

<span class="hljs-comment"># Maak voor het overzicht een variabele </span>
<span class="hljs-comment"># aan met alle benodigde NDK libraries</span>
<span class="hljs-keyword">set</span> (extraNdkLibs <span class="hljs-envvar">${android-lib}</span> <span class="hljs-envvar">${z-lib}</span> <span class="hljs-envvar">${log-lib}</span> 
    <span class="hljs-envvar">${opensl-lib}</span> <span class="hljs-envvar">${egl-lib}</span> <span class="hljs-envvar">${gles-lib}</span> )

<span class="hljs-keyword">target_link_libraries</span>( native-lib
    <span class="hljs-envvar">${extraNdkLibs}</span> <span class="hljs-comment"># Link de NDK libraries</span>
)</code></pre>

<h4 id="libzip-headers">Libzip headers</h4>

<p>De Wwise SDK komt met de binaries van libzip, maar ironisch gezien <strong>niet</strong> met de headers. Die kun je door CMake automatisch laten downloaden en toevoegen.</p>



<pre class="prettyprint"><code class="language-cmake hljs "><span class="hljs-keyword">cmake_minimum_required</span>(VERSION <span class="hljs-number">3.4</span>.<span class="hljs-number">1</span>)
<span class="hljs-keyword">include</span>(ExternalProject) <span class="hljs-comment"># Stelt de ExternalProject_Add functie ter beschikking</span>

<span class="hljs-comment"># Kloont het libzip project op Github en zet het in een nieuwe "zip" map </span>
<span class="hljs-comment"># in een eveneens nieuwe "third-party" map.</span>
ExternalProject_Add(libzip_externalproject
        GIT_REPOSITORY      git@github.com:nih-at/libzip.git
        GIT_TAG             rel-<span class="hljs-number">1</span>-<span class="hljs-number">0</span>
        PREFIX              <span class="hljs-envvar">${CMAKE_SOURCE_DIR}</span>/third-party/zip

        <span class="hljs-comment"># We bouwen dit project niet, we willen alleen de headers.</span>
        <span class="hljs-comment"># Daarom moeten we expliciet aangeven dat deze commando's </span>
        <span class="hljs-comment"># niets worden geacht te doen :-)</span>
        CONFIGURE_COMMAND   <span class="hljs-string">""</span>
        <span class="hljs-keyword">BUILD_COMMAND</span>       <span class="hljs-string">""</span>
        INSTALL_COMMAND     <span class="hljs-string">""</span>
        UPDATE_COMMAND      <span class="hljs-string">""</span> )

<span class="hljs-comment"># Voeg deze definitie's toe voor compatibiliteitsredenen</span>
<span class="hljs-comment"># Dit is het zelfde als wanneer je in C/C++ doet:</span>
<span class="hljs-comment">#</span>
<span class="hljs-comment">#     #define DSIZEOF_OFF_T 8</span>
<span class="hljs-comment">#     #define HAVE_STD_BOOL_H</span>
<span class="hljs-keyword">add_definitions</span> (-DSIZEOF_OFF_T=<span class="hljs-number">8</span> -DHAVE_STDBOOL_H)

<span class="hljs-comment"># Extraheer de map met header (.h) files en wijs die toe aan een variabele.</span>
ExternalProject_Get_Property(libzip_externalproject SOURCE_DIR)
<span class="hljs-keyword">set</span> (LIBZIP_INCLUDE_DIR <span class="hljs-envvar">${SOURCE_DIR}</span>/lib)

<span class="hljs-comment"># add_library(native-lib ... )</span>
<span class="hljs-comment"># target_link_libraries(native-lib ... )</span>

<span class="hljs-comment"># Onze library is afhankelijk van het downloadproces van libzip. </span>
<span class="hljs-comment"># Als dit wordt weggelaten, wacht de compiler niet totdat libzip </span>
<span class="hljs-comment"># is gedownload en faalt de compilatie.</span>
<span class="hljs-keyword">add_dependencies</span>(native-lib libzip_externalproject)

<span class="hljs-comment"># Voeg de headers toe aan onze library</span>
target_include_directories( native-lib PUBLIC
    <span class="hljs-envvar">${LIBZIP_INCLUDE_DIR}</span>
)</code></pre>



<h5 id="libzip-configuratie">Libzip configuratie</h5>

<p>Voor de configuratie van libzip moet het include path zijn <a href="https://github.com/nih-at/libzip/blob/rel-1-0/lib/zip.h#L59">voorzien</a> van een <code>zipconf.h</code> bestand. Download <a href="https://gist.github.com/Tomasito665/a28e296ee1474f665efd8997e227b1a8">zipconf.h</a> en zet het in dezelfde map waar onze <code>native-lib.cpp</code> code zich huisvest.</p>

<pre><code>$projectDir/app/src/main/cpp/zipconf.h
</code></pre>

<p>Voeg deze map toe aan het include path in <code>CMakeLists.txt</code>.</p>



<pre class="prettyprint"><code class="language-cmake hljs ">target_include_directories( native-lib PUBLIC
    <span class="hljs-string">"src/main/cpp"</span>
    <span class="hljs-envvar">${LIBZIP_INCLUDE_DIR}</span>
)</code></pre>



<h4 id="wwise-headers-en-libraries">Wwise headers en libraries</h4>

<p>Download <a href="https://gist.github.com/Tomasito665/3436fd7046a12d4161ca0e53808f0dec">FindWwise.cmake</a> en zet het in een nieuwe map:</p>

<pre><code>$projectDir/app/cmake-modules/FindWwise.cmake
</code></pre>

<blockquote>
  <p>Voor het vinden van de Wwise SDK maakt dit script gebruik van de $WWISE_SDK environment variable die je tijdens de installatie hebt aangemaakt.</p>
</blockquote>

<p>Stel de nieuwe map in als CMake module path in <code>CMakeLists.txt</code>. </p>



<pre class="prettyprint"><code class="language-cmake hljs "><span class="hljs-keyword">set</span>(CMAKE_MODULE_PATH <span class="hljs-envvar">${CMAKE_CURRENT_SOURCE_DIR}</span>/cmake-modules)</code></pre>

<p>Nu kun je met het <code>find_package</code> commando het <code>FindWwise</code> cmake script uitvoeren. Dat zal een aantal variabelen definiëren:</p>

<ul>
<li><code>Wwise_FOUND</code> Boolean die <code>false</code> is als de Wwise SDK niet is gevonden.</li>
<li><code>Wwise_LIBRARIES</code> De static libraries van Wwise.</li>
<li><code>Wwise_INCLUDE_DIR</code> De map met de header (.h) files van Wwise.</li>
</ul>

<p>Voeg de Wwise headers toe aan het compileerproces en link de static libraries van Wwise aan onze <code>native-lib</code> shared library.</p>



<pre class="prettyprint"><code class="language-cmake hljs "><span class="hljs-comment"># Dit commando voert het FindWwise.cmake script uit.</span>
<span class="hljs-comment"># Let er op dat dit commando ná het set(CMAKE_MODULE_PATH ... )</span>
<span class="hljs-comment"># commando moet staan.</span>
<span class="hljs-keyword">find_package</span>(Wwise)

<span class="hljs-comment"># Staak het proces met een FATAL_ERROR mocht </span>
<span class="hljs-comment"># Wwise niet zijn gevonden.</span>
<span class="hljs-keyword">if</span> (NOT Wwise_FOUND)
  <span class="hljs-keyword">message</span> (FATAL_ERROR <span class="hljs-string">"Wwise SDK not found"</span>)
<span class="hljs-keyword">endif</span>()

<span class="hljs-comment"># Voeg de Wwise headers toe</span>
target_include_directories( native-lib PUBLIC
    <span class="hljs-string">"src/main/cpp"</span>
    <span class="hljs-envvar">${LIBZIP_INCLUDE_DIR}</span>
    <span class="hljs-envvar">${Wwise_INCLUDE_DIR}</span>
)

<span class="hljs-comment"># Link de Wwise libraries met onze library</span>
<span class="hljs-keyword">target_link_libraries</span>( native-lib
    <span class="hljs-envvar">${extraNdkLibs}</span>
    <span class="hljs-envvar">${Wwise_LIBRARIES}</span>
)</code></pre>

<h2 id="soundengine-io">SoundEngine I/O</h2>

<p>De functionaliteit om Wwise Soundbanks te kunnen openen zit niet standaard in de Wwise SDK. Daarom moeten wij die zelf toevoegen en compileren. Gelukkig zit alle nodige code in het <code>SoundEngine</code> voorbeeld project, wat te vinden is in: <code>$WWISE_SDK/samples/SoundEngine</code>. De map ziet er als volgt uit:</p>

<pre><code>SoundEngine
 |- Android
 |   |- zipzip
 |       |- ...
 |   |- AkDefaultIOHookBlocking.cpp
 |   |- AkDefaultIOHookBlocking.h
 |   |- etc.
 |- Common
 |   |- AkDefaultLowLevelIODispatcher.cpp
 |   |- AkDefaultLowLevelIODispatcher.h
 |   |- etc.
 |- POSIX
 |- Win32
</code></pre>

<p>Maak een nieuwe map aan in ons project: <code>$projectDir/app/src/main/cpp/wwise</code> en kopiëer de <code>SoundEngine</code> map daar naartoe.</p>

<pre><code>$projectDir/app/src/main/cpp/wwise/SoundEngine
</code></pre>

<p>Kopiëer het <code>stdafx.h</code> bestand van <code>SoundEngine/POSIX</code> naar <code>SoundEngine/Android</code> en naar <code>SoundEngine/Common</code>. Na het kopiëren hebben we de volgende mappen niet meer nodig. Voel je vrij om deze te verwijderen:</p>

<pre><code>$projectDir/app/src/main/cpp/wwise/SoundEngine/Android/libzip
$projectDir/app/src/main/cpp/wwise/SoundEngine/POSIX
$projectDir/app/src/main/cpp/wwise/SoundEngine/Win32
</code></pre>

<p>De mappen structuur ziet er binnen Android Studio nu als volgt uit.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/-Fk9embDNXr4/WQ-AXPyDJsI/AAAAAAAAJtY/3WNXpLBqS2MbErhg8koe6KeDTyEWiCPogCE0/s550/mappenstructuurAndroidStudio.PNG" alt="Android Studio - Mappenstructuur" title="Mappenstructuur"></center><p></p>

<p>Voeg de bronbestanden van de code in de <code>SoundEngine</code> map toe aan onze <code>native-lib</code> library. Voeg ook de mappen <code>SoundEngine/Android</code> en <code>SoundEngine/Common</code> toe aan het include path.</p>

<pre class="prettyprint"><code class="language-cmake hljs "><span class="hljs-keyword">set</span> (WWISE_IO_COMMON_DIR src/main/cpp/wwise/SoundEngine/Common)
<span class="hljs-keyword">set</span> (WWISE_IO_ANDROID_DIR src/main/cpp/wwise/SoundEngine/Android)

<span class="hljs-keyword">set</span> ( WWISE_IO_SRC_FILES
  <span class="hljs-envvar">${WWISE_IO_COMMON_DIR}</span>/AkDefaultLowLevelIODispatcher.cpp
  <span class="hljs-envvar">${WWISE_IO_COMMON_DIR}</span>/AkFileLocationBase.cpp
  <span class="hljs-envvar">${WWISE_IO_COMMON_DIR}</span>/AkFilePackage.cpp
  <span class="hljs-envvar">${WWISE_IO_COMMON_DIR}</span>/AkFilePackageLUT.cpp
  <span class="hljs-envvar">${WWISE_IO_ANDROID_DIR}</span>/AkDefaultIOHookBlocking.cpp
  <span class="hljs-envvar">${WWISE_IO_ANDROID_DIR}</span>/AkDefaultIOHookDeferred.cpp
  <span class="hljs-envvar">${WWISE_IO_ANDROID_DIR}</span>/AkFileHelpers.cpp )

<span class="hljs-comment"># Voeg de bronbestanden toe aan onze library</span>
<span class="hljs-keyword">add_library</span>( native-lib
             SHARED
             src/main/cpp/native-lib.cpp
             <span class="hljs-envvar">${WWISE_IO_SRC_FILES}</span> )

<span class="hljs-comment"># Voeg de nieuwe directories toe aan het include path</span>
target_include_directories( native-lib PUBLIC
    <span class="hljs-string">"src/main/cpp"</span>
    <span class="hljs-envvar">${LIBZIP_INCLUDE_DIR}</span>
    <span class="hljs-envvar">${Wwise_INCLUDE_DIR}</span>
    <span class="hljs-envvar">${WWISE_IO_COMMON_DIR}</span>
    <span class="hljs-envvar">${WWISE_IO_ANDROID_DIR}</span>
)</code></pre>

<blockquote>
  <p>Als je na deze stap probeert de bouwen en de linker klaagt over missende implementatie’s, geen paniek. Dit is normaal. Het klopt dat de functie’s <code>AK::AllocHook(unsigned long)</code> en <code>AK::FreeHook(void*)</code> nog niet zijn geïmplementeerd. Hier kijken we later naar.</p>
</blockquote>

<h2 id="wwise-hello-world-soundbank">Wwise Hello-world SoundBank</h2>

<p>Voor deze tutorial gaan we een basis soundbank maken met één geluid en één event die dat geluid triggert. Open Wwise en maak een nieuw project aan. Voeg daarbij het <code>Android</code> platform toe.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/-0P3ZeGfFRtQ/WQ-LAvDKSwI/AAAAAAAAJtw/oiCba5UW2T0ldtX5MXCvOBBTSeokDJ3-ACE0/s475/WwiseNewProject.PNG" alt="Wwise - New Project" title="New Project"></center><p></p>

<p>Sleep een geluidsbestand naar keuze in de <code>Actor-Mixer Hierarchy</code> map in Wwise. Klik daarna met de rechter muisknop op het ingesleepte bestand en klik vervolgens op <code>Convert</code>. Vink het <code>Android</code> platform aan en klik op <code>OK</code>.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/-fX35o4iGkb4/WQ-MBDbMvoI/AAAAAAAAJuE/wEqJtfEss2MdvHtCm-J-MAoTVAwo1MBsgCE0/s475/WwiseConvertAudio.PNG" alt="Wwise - Convert..." title="Convert...">&nbsp;&nbsp;&nbsp;<img src="https://lh3.googleusercontent.com/-mRvDlaDv0CI/WQ-M1yTVFnI/AAAAAAAAJuk/VpWRuV6erRYjAydInmq6z9jZfW3TGE9MQCE0/s300/WwiseAudioFileConversion.PNG" alt="Wwise - Audio File Conversion Dialog" title="Audio File Conversion Dialog"></center><p></p>

<p>Maak een nieuw <code>Play</code> event aan en noem dat <code>HELLO_PLAY</code>.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/-9FYSXBragqU/WQ-ONbIRXYI/AAAAAAAAJvE/wqlzZY0Ua_0VVTku5a7AQklcOP3B9sBDgCE0/s300/WwiseNewEvent.PNG" alt="Wwise - New Event" title="New Event">&nbsp;&nbsp;&nbsp;<img src="https://lh3.googleusercontent.com/-ZVS7yPwxAko/WQ-O-VUQfwI/AAAAAAAAJvo/AbrEVq5VJRk0a02Ernqni14icRDY6PbiACE0/s300/WwiseEventName.PNG" alt="Wwise - Event Name" title="Event Name"></center><p></p>

<p>Open de <code>SoundBank Manager</code> view door op de <code>F7</code> toets te drukken. Maak een nieuwe soundbank aan en noem deze <code>Main</code>. Voeg het <code>HELLO_PLAY</code> event daar aan toe. Vink het <code>Android</code> platform aan en op z’n minst één taal in het <code>Languages</code> paneel. Druk op de <code>Generate</code> knop om de soundbank te bouwen.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/-RQAmWKNoMhs/WQ-QNdLZmpI/AAAAAAAAJv4/O2dZYiNI9sIhbTVLXRPsx2y7ZEuWTEW9QCE0/s500/WwiseSoundBankManager.PNG" alt="Wwise - SoundBank Manager" title="SoundBank Manager"></center><p></p>

<h3 id="soundbank-importeren-in-android-studio">Soundbank importeren in Android Studio</h3>

<p>Er van uitgaande dat het Wwise project <code>HelloWorld</code> heet, staat de gegenereerde soundbank in: </p>

<pre><code>$HOME/WwiseProjects/HelloWorld/GeneratedSoundBanks/Android
</code></pre>

<p>Maak in Android Studio twee nieuwe mappen aan:</p>

<pre><code>$projectDir/app/src/main/assets
$projectDir/app/src/main/assets/soundbank
</code></pre>

<p>Kopiëer alle bestanden uit <code>GeneratedSoundBanks/Android</code> en plak ze in de nieuwe <code>soundbank</code> map. Het Project View venster in Android Studio ziet er nu als volgt uit.</p>

<p></p><center><img src="https://lh3.googleusercontent.com/-YCL-XVdkTnk/WQ-TwQ7T9XI/AAAAAAAAJwU/8NizS7o4G6gsSX2p4QkzZ9nr4nYXRzBHgCE0/s500/Android+Studio+-+soundbank.PNG" alt="Android Studio - Project view soundbank folder" title="Soundbank directory"></center><p></p>

<blockquote>
  <p>De nieuw gecreëerde map heeft een speciale naam: “assets”. Door die naam weet Android Studio dat de inhoud van die map meegeleverd moet worden in de APK. Dat zie je tevens ook aan het speciale icoontje in de Project View.</p>
</blockquote>



<h2 id="java-native-interface">Java Native Interface</h2>

<p>Om vanuit Java gebruik te kunnen maken van de functie’s uit de Wwise SDK gaan wij een class maken in Java, waarvan de methods als <code>native</code> staan gemarkeerd en worden geïmplementeerd in C++, waarin we gebruik kunnen maken van de Wwise SDK.</p>



<h3 id="java">Java</h3>

<p>Maak een nieuwe Java class aan in dezelfde map als de <code>MainActivity</code> class en noem die <em>SoundEngine</em>. Maak van deze class een singleton <a href="#fn:singleton" id="fnref:singleton" title="See footnote" class="footnote">11</a> en laadt de <code>native-lib</code> library in met de <code>System#loadLibrary</code> functie. Geef de class drie met <code>native</code> gemarkeerde methods: <code>SoundEngine#init()</code>, <code>SoundEngine#loadBank(String)</code> en <code>SoundEngine#postEvent(String)</code>. Laat ze alle drie een <code>boolean</code> teruggeven. Voeg ook een <code>SoundEngine#init(Activity)</code> method toe, wederom gemarkeerd met het <code>native</code> keyword. Laat deze method niets terug geven.</p>



<pre class="prettyprint"><code class="language-java hljs "><span class="hljs-keyword">import</span> android.app.Activity;

<span class="hljs-keyword">public</span> <span class="hljs-keyword">final</span> <span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">SoundEngine</span> {</span>
    <span class="hljs-keyword">static</span> {
        <span class="hljs-comment">// Laadt onze native-lib C++ library in</span>
        System.loadLibrary(<span class="hljs-string">"native-lib"</span>);
    }

    <span class="hljs-comment">// De singleton instantie</span>
    <span class="hljs-keyword">private</span> <span class="hljs-keyword">static</span> SoundEngine sInstance = <span class="hljs-keyword">null</span>;

    <span class="hljs-javadoc">/**
     * Laat niemand deze class instantiëren.
     */</span>
    <span class="hljs-keyword">private</span> <span class="hljs-title">SoundEngine</span>() { }

    <span class="hljs-javadoc">/**
     * Geeft de SoundEngine singleton instantie terug
     */</span>
    <span class="hljs-keyword">public</span> <span class="hljs-keyword">static</span> SoundEngine <span class="hljs-title">getInstance</span>() {
        <span class="hljs-keyword">if</span> (sInstance == <span class="hljs-keyword">null</span>) {
            sInstance = <span class="hljs-keyword">new</span> SoundEngine();
        }

        <span class="hljs-keyword">return</span> sInstance;
    }

    <span class="hljs-javadoc">/**
     * Initialiseert de C++ code
     * 
     *<span class="hljs-javadoctag"> @param</span> activity de hoofd Activity van de app
     *<span class="hljs-javadoctag"> @return</span> &lt;code&gt;false&lt;/code&gt; als de initialisatie mislukt
     */</span>
    <span class="hljs-keyword">public</span> <span class="hljs-keyword">native</span> <span class="hljs-keyword">boolean</span> <span class="hljs-title">init</span>(Activity activity);

    <span class="hljs-javadoc">/**
     * Laadt een soundbank.
     * 
     *<span class="hljs-javadoctag"> @param</span> name naam van de soundbank. Bijvoorbeeld: Main.bnk
     *<span class="hljs-javadoctag"> @return</span> &lt;code&gt;false&lt;/code&gt; als er iets mis ging tijdens 
     *         het laden
     */</span>
    <span class="hljs-keyword">public</span> <span class="hljs-keyword">native</span> <span class="hljs-keyword">boolean</span> <span class="hljs-title">loadBank</span>(String name);

    <span class="hljs-javadoc">/**
     * Stuurt een event naar de Wwise SoundEngine
     * 
     *<span class="hljs-javadoctag"> @param</span> id de naam van het event
     *<span class="hljs-javadoctag"> @return</span> &lt;code&gt;false&lt;/code&gt; als de gegeven event-id niet bestaat
     */</span>
    <span class="hljs-keyword">public</span> <span class="hljs-keyword">native</span> <span class="hljs-keyword">boolean</span> <span class="hljs-title">postEvent</span>(String id);
}</code></pre>

<h3 id="c">C++</h3>

<p>De methods die met <code>native</code> staan gemarkeerd in de <code>SoundEngine</code> Java class ga je implementeren in het <code>native-lib.cpp</code> bestand. Voeg de volgende includes en defines toe.</p>

<pre class="prettyprint"><code class="language-cpp hljs "><span class="hljs-preprocessor">#include &lt;jni.h&gt;</span>
<span class="hljs-preprocessor">#include &lt;string&gt;</span>

<span class="hljs-comment">// Wwise headers. Dubbelcheck dat ${Wwise_INCLUDE_DIR} in de</span>
<span class="hljs-comment">// include path staat in CMakeLists.txt</span>
<span class="hljs-preprocessor">#include &lt;AK/Tools/Common/AkPlatformFuncs.h&gt;</span>
<span class="hljs-preprocessor">#include &lt;AK/SoundEngine/Common/IAkStreamMgr.h&gt;</span>
<span class="hljs-preprocessor">#include &lt;AK/SoundEngine/Common/AkSoundEngine.h&gt;</span>
<span class="hljs-preprocessor">#include &lt;AK/SoundEngine/Common/AkStreamMgrModule.h&gt;</span>
<span class="hljs-preprocessor">#include &lt;AK/SoundEngine/Common/AkModule.h&gt;</span>
<span class="hljs-preprocessor">#include &lt;AK/MusicEngine/Common/AkMusicEngine.h&gt;</span>

<span class="hljs-comment">// Negeer de waarschuwing van Android Studio dat deze include</span>
<span class="hljs-comment">// niet zou worden gebruikt. Deze include is zeer belangrijk</span>
<span class="hljs-comment">// om de Wwise plugins te kunnen gebruiken, zoals SynthOne.</span>
<span class="hljs-preprocessor">#include &lt;AK/Plugin/AllPluginsFactories.h&gt;</span>

<span class="hljs-comment">// De CommunicationCentral library is niet meegeleverd in</span>
<span class="hljs-comment">// release builds. De headers Communication headers heb je</span>
<span class="hljs-comment">// dus niet nodig in release. AK_OPTIMIZED is alleen</span>
<span class="hljs-comment">// gedefiniëerd bij release builds.</span>
<span class="hljs-preprocessor">#ifndef AK_OPTIMIZED</span>
<span class="hljs-preprocessor">#include &lt;AK/Comm/AkCommunication.h&gt;</span>
<span class="hljs-preprocessor">#endif</span>

<span class="hljs-comment">// Één van de headers die je hebt toegevoegd in de SoundEngine I/O</span>
<span class="hljs-comment">// fase van de tutorial. Dubbelcheck dat de ${WWISE_IO_ANDROID_DIR}</span>
<span class="hljs-comment">// in de include path staat in CMakeLists.txt</span>
<span class="hljs-preprocessor">#include &lt;AkFilePackageLowLevelIOBlocking.h&gt;</span>

<span class="hljs-comment">// Dit gaan we straks gebruiken voor het verzenden van events.</span>
<span class="hljs-preprocessor">#define WWISE_INTEGRATIE_GAME_OBJ_ID 10</span></code></pre>

<p>De volgende functie’s staan gemarkeerd als <code>extern "C"</code> in de Wwise headers. De programmeur wordt geacht deze te implementeren.</p>

<pre class="prettyprint"><code class="language-c++ hljs cpp"><span class="hljs-keyword">namespace</span> AK {
    <span class="hljs-keyword">void</span> *AllocHook(size_t size) {
        <span class="hljs-keyword">return</span> <span class="hljs-built_in">malloc</span>(size);
    }

    <span class="hljs-keyword">void</span> FreeHook(<span class="hljs-keyword">void</span> *ptr) {
        <span class="hljs-built_in">free</span>(ptr);
    }
}</code></pre>

<p>Declareer de volgende globale variabelen. Deze variabelen zullen allemaal worden geïnitialiseerd in de implementatie van <code>SoundEngine#init(Activity)</code>.</p>

<pre class="prettyprint"><code class="language-cpp hljs "><span class="hljs-comment">// Pointer naar the JavaVM</span>
<span class="hljs-keyword">static</span> JavaVM *g_VM = <span class="hljs-keyword">nullptr</span>;

<span class="hljs-comment">// Weak reference naar de main activity Java instantie</span>
<span class="hljs-keyword">static</span> jweak g_activity = <span class="hljs-keyword">nullptr</span>;

<span class="hljs-comment">// Weak reference naar de Java SoundEngine singleton instantie</span>
<span class="hljs-keyword">static</span> jweak g_instance;

<span class="hljs-comment">// Low-level IO helper class</span>
<span class="hljs-keyword">static</span> CAkFilePackageLowLevelIOBlocking *g_pLowLevelIo = <span class="hljs-keyword">nullptr</span>;</code></pre>

<p>Voeg de volgende twee functie’s toe:</p>

<ul>
<li><code>log</code>, een helper functie om berichten te printen naar de logcat <a href="#fn:logcat" id="fnref:logcat" title="See footnote" class="footnote">12</a>.</li>
<li><code>initWwise</code>, initialiseert verschillende onderdelen van Wwise: <br>
<ul><li>Memory Manager</li>
<li>Stream Manager</li>
<li>Streaming Device</li>
<li>Sound Engine ( &lt;- het hart, waar alles op is aangesloten)</li>
<li>Music Engine</li>
<li>Communication Device (voor connectie met de Wwise authoring tools)</li></ul></li>
</ul>



<pre class="prettyprint"><code class="language-c++ hljs lasso"><span class="hljs-comment">// Print een bericht naar de logcat terminal</span>
<span class="hljs-literal">void</span> <span class="hljs-keyword">log</span>(const std<span class="hljs-tag">::string</span> <span class="hljs-subst">&amp;</span>msg, 
         android_LogPriority logPriority <span class="hljs-subst">=</span> ANDROID_LOG_INFO) {
    __android_log_print(logPriority, <span class="hljs-string">"WwiseIntegratie"</span>, <span class="hljs-string">"%s"</span>, msg<span class="hljs-built_in">.</span>c_str());
}

<span class="hljs-comment">// Initialiseert Wwise</span>
bool initWwise() {

    <span class="hljs-comment">// Memory Manager</span>
    AkMemSettings memSettings;
    memSettings<span class="hljs-built_in">.</span>uMaxNumPools <span class="hljs-subst">=</span> <span class="hljs-number">20</span>;
    <span class="hljs-keyword">if</span> (AK<span class="hljs-tag">::MemoryMgr</span><span class="hljs-tag">::Init</span>(<span class="hljs-subst">&amp;</span>memSettings) <span class="hljs-subst">!=</span> AK_Success) {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"AK::MemoryMgr::Init failed"</span>, ANDROID_LOG_ERROR);
        <span class="hljs-keyword">return</span> <span class="hljs-literal">false</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Memory Manager initialized"</span>);
    }

    <span class="hljs-comment">// Stream Manager</span>
    AkStreamMgrSettings stmSettings;
    AK<span class="hljs-tag">::StreamMgr</span><span class="hljs-tag">::GetDefaultSettings</span>(stmSettings);
    <span class="hljs-keyword">if</span> (<span class="hljs-subst">!</span>AK<span class="hljs-tag">::StreamMgr</span><span class="hljs-tag">::Create</span>(stmSettings)) {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"AK::StreamMgr::Create failed"</span>, ANDROID_LOG_ERROR);
        <span class="hljs-keyword">return</span> <span class="hljs-literal">false</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Stream Manager initialized"</span>);
    }

    <span class="hljs-comment">// Streaming device (pLowLevelIO points to a</span>
    <span class="hljs-comment">// CAkFilePackageLowLevelIOBlocking object)</span>
    AkDeviceSettings deviceSettings;
    AK<span class="hljs-tag">::StreamMgr</span><span class="hljs-tag">::GetDefaultDeviceSettings</span>(deviceSettings);
    <span class="hljs-keyword">if</span> (g_pLowLevelIo<span class="hljs-subst">-&gt;</span>Init(deviceSettings) <span class="hljs-subst">!=</span> AK_Success) {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"CAkFilePackageLowLevelIOBlocking:Init failed"</span>, ANDROID_LOG_ERROR);
        <span class="hljs-keyword">return</span> <span class="hljs-literal">false</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Streaming Device initialized"</span>);
    }

    const char <span class="hljs-subst">*</span>basepath <span class="hljs-subst">=</span> <span class="hljs-string">"soundbank"</span>;
    <span class="hljs-keyword">if</span> (g_pLowLevelIo<span class="hljs-subst">-&gt;</span>SetBasePath(basepath) <span class="hljs-subst">!=</span> AK_Success) {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Error setting base path to streaming device"</span>, ANDROID_LOG_ERROR);
        <span class="hljs-keyword">return</span> <span class="hljs-literal">false</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-keyword">log</span>(std<span class="hljs-tag">::string</span>(<span class="hljs-string">"Streaming Device base path set to '"</span>) <span class="hljs-subst">+</span> basepath <span class="hljs-subst">+</span> <span class="hljs-string">"'"</span>);
    }

    <span class="hljs-comment">// Sound Engine</span>
    AkInitSettings initSettings;
    AkPlatformInitSettings platformInitSettings;
    AK<span class="hljs-tag">::SoundEngine</span><span class="hljs-tag">::GetDefaultInitSettings</span>(initSettings);
    AK<span class="hljs-tag">::SoundEngine</span><span class="hljs-tag">::GetDefaultPlatformInitSettings</span>(platformInitSettings);

    <span class="hljs-comment">// Hoewel Wwise gemaakt is voor native activity, kan </span>
    <span class="hljs-comment">// hier ook de Java activity worden opgegeven. Dit is </span>
    <span class="hljs-comment">// cruciaal, anders kan Wwise niet communiceren met het</span>
    <span class="hljs-comment">// Android OS en geen geluid maken. </span>
    platformInitSettings<span class="hljs-built_in">.</span>pJavaVM <span class="hljs-subst">=</span> g_VM;
    platformInitSettings<span class="hljs-built_in">.</span>jNativeActivity <span class="hljs-subst">=</span> g_activity;

    <span class="hljs-keyword">if</span> (AK<span class="hljs-tag">::SoundEngine</span><span class="hljs-tag">::Init</span>(<span class="hljs-subst">&amp;</span>initSettings, <span class="hljs-subst">&amp;</span>platformInitSettings) <span class="hljs-subst">!=</span> AK_Success) {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"SoundEngine::Init failed"</span>, ANDROID_LOG_ERROR);
        <span class="hljs-keyword">return</span> <span class="hljs-literal">false</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Sound Engine initialized"</span>);
    }

    AK<span class="hljs-tag">::SoundEngine</span><span class="hljs-tag">::RegisterGameObj</span>(WWISE_INTEGRATIE_GAME_OBJ_ID);

    <span class="hljs-comment">// Music Engine</span>
    AkMusicSettings musicSettings;
    AK<span class="hljs-tag">::MusicEngine</span><span class="hljs-tag">::GetDefaultInitSettings</span>(musicSettings);
    <span class="hljs-keyword">if</span> (AK<span class="hljs-tag">::MusicEngine</span><span class="hljs-tag">::Init</span>(<span class="hljs-subst">&amp;</span>musicSettings) <span class="hljs-subst">!=</span> AK_Success) {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"MusicEngine::Init failed"</span>, ANDROID_LOG_ERROR);
        <span class="hljs-keyword">return</span> <span class="hljs-literal">false</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Music Engine initialized"</span>);
    }

    <span class="hljs-comment">// Communication device</span>
<span class="hljs-variable">#ifndef</span> AK_OPTIMIZED
    AkCommSettings commSettings;
    AK<span class="hljs-tag">::Comm</span><span class="hljs-tag">::GetDefaultInitSettings</span>(commSettings);
    commSettings<span class="hljs-built_in">.</span>ports<span class="hljs-built_in">.</span>uDiscoveryBroadcast <span class="hljs-subst">=</span> <span class="hljs-number">24024</span>; <span class="hljs-comment">// Default port</span>
    <span class="hljs-keyword">if</span> (AK<span class="hljs-tag">::Comm</span><span class="hljs-tag">::Init</span>(commSettings) <span class="hljs-subst">!=</span> AK_Success) {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Comm::Init failed"</span>, ANDROID_LOG_ERROR);
        <span class="hljs-comment">// Als dit faalt, check of je INTERNET machtiging </span>
        <span class="hljs-comment">// goed staat in AndroidManifest.xml</span>
        <span class="hljs-keyword">return</span> <span class="hljs-literal">false</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-keyword">log</span>(<span class="hljs-string">"Communication Module initialized"</span>);
    }
<span class="hljs-variable">#endif</span>

    <span class="hljs-keyword">return</span> <span class="hljs-literal">true</span>;
}</code></pre>

<h4 id="native-method-implementaties">Native method implementatie’s</h4>

<p>De implementatie’s van <code>native</code> Java methods vereisen een stricte naamgeving. Die is als volgt <code>Java_%1_%2</code>, waar:</p>

<ul>
<li>%1 gelijk staat tot de Fully Qualified Java Class Name <a href="#fn:fully_qualified_java_class_name" id="fnref:fully_qualified_java_class_name" title="See footnote" class="footnote">13</a> van de desbetreffende Java class.</li>
<li>%2 gelijk staat tot de naam van de desbetreffende <code>native</code> method</li>
</ul>

<p>Verder ontvangt de C++ implementatie te allen tijde minimaal twee argumenten:</p>

<ol>
<li><code>JNIEnv*</code> is een pointer naar de JNI omgeving.</li>
<li><code>jobject</code> is een referentie naar <code>this</code> van de desbetreffende Java class. Mocht je bekend zijn met Python: dit is vergelijkbaar met het eerste <code>self</code> argument in Python class methods.</li>
</ol>

<p>Het eerste argument aan de Java kant, is het derde argument aan de C++ kant. Het tweede aan de Java kant, het vierde aan de C++ kant, enz.</p>



<pre class="prettyprint"><code class="language-java hljs ">class Foo {
  <span class="hljs-keyword">void</span> <span class="hljs-keyword">native</span> bar(String baz);
}</code></pre>



<pre class="prettyprint"><code class="language-cpp hljs "><span class="hljs-keyword">extern</span> <span class="hljs-string">"C"</span>
Java_package_Foo_bar(JNIEnv *env, jobject thiz, jstring baz) { }</code></pre>

<p>Implementeer <code>SoundEngine#init(Activity)</code> en initialiseer daarbij de globale variabelen die je net hebt gedeclareerd.</p>

<blockquote>
  <p>In dit voorbeeld hanteer ik de Java class naam <em>nl.jordiortola.WwiseIntegratie.SoundEngine</em>. Bij jou zal die ongetwijfeld anders zijn, let er dus op dat je functienam klopt.</p>
</blockquote>



<pre class="prettyprint"><code class="language-cpp hljs "><span class="hljs-comment">// JNI implementatie van SoundEngine#init(Activity)</span>
<span class="hljs-keyword">extern</span> <span class="hljs-string">"C"</span>
JNIEXPORT jboolean JNICALL
Java_nl_jordiortola_wwiseintegratie_SoundEngine_init(
        JNIEnv *env, 
        jobject instance, 
        jobject activity) {

  <span class="hljs-comment">// Cache de JavaVM</span>
  env-&gt;GetJavaVM(&amp;g_VM);

  <span class="hljs-comment">// Cache activity and SoundController Java instance ("this")</span>
  g_activity = env-&gt;NewWeakGlobalRef(activity);
  g_instance = env-&gt;NewWeakGlobalRef(instance);

  <span class="hljs-comment">// Initialiseer IO, geef false terug als dat niet lukt</span>
  g_pLowLevelIo = <span class="hljs-keyword">new</span> CAkFilePackageLowLevelIOBlocking();
  <span class="hljs-keyword">if</span> ((g_pLowLevelIo-&gt;InitAndroidIO(g_VM, g_activity)) != AK_Success) {
    <span class="hljs-keyword">return</span> (jboolean) <span class="hljs-keyword">false</span>;
  }

  <span class="hljs-comment">// Initializeer Wwise, geef false terug als dat niet lukt</span>
  <span class="hljs-keyword">return</span> (jboolean) initWwise();
}</code></pre>

<p>Implementeer de overige twee <code>native</code> <code>SoundEngine</code> methods.</p>

<pre class="prettyprint"><code class="language-cpp hljs "><span class="hljs-comment">// JNI implementatie van SoundEngine#postEvent(String)</span>
<span class="hljs-keyword">extern</span> <span class="hljs-string">"C"</span>
JNIEXPORT jboolean JNICALL
Java_nl_jordiortola_wwiseintegratie_SoundEngine_postEvent(
        JNIEnv *env, 
        jobject <span class="hljs-comment">/* instance */</span>, 
        jstring eventName_) {

  <span class="hljs-keyword">const</span> <span class="hljs-keyword">char</span> *eventName = env-&gt;GetStringUTFChars(eventName_, <span class="hljs-number">0</span>);

  <span class="hljs-comment">// Retrieve the event ID for the given name and post the event</span>
  AkUInt32 id = AK::SoundEngine::GetIDFromString(eventName);
  AkPlayingID res = AK::SoundEngine::PostEvent(id, WWISE_INTEGRATIE_GAME_OBJ_ID);
  AK::SoundEngine::RenderAudio();

  env-&gt;ReleaseStringUTFChars(eventName_, eventName);
  <span class="hljs-keyword">return</span> jboolean (res != AK_INVALID_PLAYING_ID);
}

<span class="hljs-comment">// JNI implementatie van SoundEngine#loadBank(String)</span>
<span class="hljs-keyword">extern</span> <span class="hljs-string">"C"</span>
JNIEXPORT jboolean JNICALL
Java_nl_jordiortola_wwiseintegratie_SoundEngine_loadBank(
        JNIEnv *env,
        jobject <span class="hljs-comment">/* instance */</span>,
        jstring path_) {

    <span class="hljs-keyword">const</span> <span class="hljs-keyword">char</span> *path = env-&gt;GetStringUTFChars(path_, <span class="hljs-number">0</span>);

    AkBankID bankId;
    AKRESULT res = AK::SoundEngine::LoadBank(path, AK_DEFAULT_POOL_ID, bankId);
    <span class="hljs-built_in">log</span>(<span class="hljs-string">"SoundEngine::LoadBank loading "</span> + <span class="hljs-built_in">std</span>::<span class="hljs-built_in">string</span>(path));
    env-&gt;ReleaseStringUTFChars(path_, path);

    <span class="hljs-keyword">if</span> (res != AK_Success) {
        <span class="hljs-built_in">log</span>(<span class="hljs-string">"SoundEngine::LoadBank failed"</span> , ANDROID_LOG_ERROR);
        <span class="hljs-keyword">return</span> (jboolean) <span class="hljs-keyword">false</span>;
    }

    <span class="hljs-keyword">return</span> (jboolean) <span class="hljs-keyword">true</span>;
}</code></pre>

<h2 id="de-app">De app</h2>

<p>Alle Wwise code is nu geprepareerd en klaar voor gebruik. De code voor de app wordt geschreven in de <code>MainActivity</code> class. Initialiseer de <code>SoundEngine</code> in de <code>MainActivity#onCreate(Bundle)</code> method. Maak ook een field aan aan voor de event naam die we later naar Wwise gaan versturen.</p>



<pre class="prettyprint"><code class="language-java hljs "><span class="hljs-keyword">public</span> <span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">MainActivity</span> <span class="hljs-keyword">extends</span> <span class="hljs-title">AppCompatActivity</span> {</span>

    <span class="hljs-comment">// Event naam, zoals gespecificeerd in het Wwise project</span>
    <span class="hljs-keyword">private</span> <span class="hljs-keyword">static</span> <span class="hljs-keyword">final</span> String EVENT = <span class="hljs-string">"HELLO_PLAY"</span>;

    <span class="hljs-annotation">@Override</span>
    <span class="hljs-keyword">protected</span> <span class="hljs-keyword">void</span> <span class="hljs-title">onCreate</span>(Bundle savedInstanceState) {
        <span class="hljs-keyword">super</span>.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        <span class="hljs-comment">// Initialiseer de SoundEngine en laadt de soundbanks in. </span>
        <span class="hljs-comment">// Sla in de result variabele true op als zowel het </span>
        <span class="hljs-comment">// initialiseren als het laden van de soundbanks goed ging.</span>
        SoundEngine sndEngine = SoundEngine.getInstance();
        <span class="hljs-keyword">boolean</span> result = sndEngine.init(<span class="hljs-keyword">this</span>)
                &amp;&amp; sndEngine.loadBank(<span class="hljs-string">"Init.bnk"</span>)
                &amp;&amp; sndEngine.loadBank(<span class="hljs-string">"Main.bnk"</span>);
    }
}
</code></pre>

<p>Maak een knop aan in de <code>activity_main.xml</code> layout resource. Indien je in Design mode zit, druk onder aan het scherm op de Text knop om de XML te kunnen aanpassen.</p>

<blockquote>
  <p>Tip: druk twee maal achter elkaar de Shift toets in om een bestand binnen het project te zoeken.</p>
</blockquote>

<pre class="prettyprint"><code class="language-xml hljs "><span class="hljs-pi">&lt;?xml version="1.0" encoding="utf-8"?&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-title">android.support.constraint.ConstraintLayout
</span>  <span class="hljs-attribute">...</span> &gt;</span>

    <span class="hljs-tag">&lt;<span class="hljs-title">Button
</span>        <span class="hljs-attribute">android:id</span>=<span class="hljs-value">"@+id/sendPlatEventBtn"</span>
        <span class="hljs-attribute">android:layout_height</span>=<span class="hljs-value">"wrap_content"</span>
        <span class="hljs-attribute">android:layout_width</span>=<span class="hljs-value">"match_parent"</span>
        <span class="hljs-attribute">android:text</span>=<span class="hljs-value">"Send HELLO_PLAY event"</span>
        <span class="hljs-attribute">android:enabled</span>=<span class="hljs-value">"false"</span>
        <span class="hljs-attribute">android:onClick</span>=<span class="hljs-value">"handleSendPlayEventBtnPress"</span>
        <span class="hljs-attribute">tools:layout_constraintTop_creator</span>=<span class="hljs-value">"1"</span>
        <span class="hljs-attribute">tools:layout_constraintRight_creator</span>=<span class="hljs-value">"1"</span>
        <span class="hljs-attribute">android:layout_marginStart</span>=<span class="hljs-value">"8dp"</span>
        <span class="hljs-attribute">android:layout_marginEnd</span>=<span class="hljs-value">"8dp"</span>
        <span class="hljs-attribute">app:layout_constraintRight_toRightOf</span>=<span class="hljs-value">"parent"</span>
        <span class="hljs-attribute">tools:layout_constraintLeft_creator</span>=<span class="hljs-value">"1"</span>
        <span class="hljs-attribute">app:layout_constraintLeft_toLeftOf</span>=<span class="hljs-value">"parent"</span>
        <span class="hljs-attribute">app:layout_constraintTop_toTopOf</span>=<span class="hljs-value">"parent"</span>/&gt;</span>

<span class="hljs-tag">&lt;/<span class="hljs-title">android.support.constraint.ConstraintLayout</span>&gt;</span></code></pre>

<p></p><center><img src="https://lh3.googleusercontent.com/-bRxmAfimKPw/WQ_EoV1ed-I/AAAAAAAAJxQ/Yr8v2cJ0WII7bGpurgUGfR1iHdIruLn4ACE0/s650/Android+Studio+-+activity_main+layout+xml.PNG" alt="Android Studio - activity_main.xml layout resource" title="activity_main.xml layout resource"></center><p></p>

<p>Schakel de knop in zodra de <code>SoundEngine</code> met success is geïnitialiseerd. Voeg vervolgens de click handler toe en stuur het Wwise event.</p>

<pre class="prettyprint"><code class="language-java hljs "><span class="hljs-keyword">public</span> <span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">MainActivity</span> <span class="hljs-keyword">extends</span> <span class="hljs-title">AppCompatActivity</span> {</span>

    <span class="hljs-annotation">@Override</span>
    <span class="hljs-keyword">protected</span> <span class="hljs-keyword">void</span> <span class="hljs-title">onCreate</span>(Bundle savedInstanceState) {
        <span class="hljs-keyword">super</span>.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        SoundEngine sndEngine = SoundEngine.getInstance();
        <span class="hljs-keyword">boolean</span> result = sndEngine.init(<span class="hljs-keyword">this</span>)
                &amp;&amp; sndEngine.loadBank(<span class="hljs-string">"Init.bnk"</span>)
                &amp;&amp; sndEngine.loadBank(<span class="hljs-string">"Main.bnk"</span>);

        <span class="hljs-comment">// Zet de button op enabled als de SoundEngine klaar is om </span>
        <span class="hljs-comment">// het geluid af te spelen.</span>
        Button btn = (Button) findViewById(R.id.sendPlatEventBtn);
        btn.setEnabled(result);
    }

    <span class="hljs-keyword">public</span> <span class="hljs-keyword">void</span> <span class="hljs-title">handleSendPlayEventBtnPress</span>(View view) {
        SoundEngine.getInstance().postEvent(EVENT);
    }
}
</code></pre>

<p>Druk in Android Studio <code>Ctrl + F10</code> in, start de app, druk op de knop en voilà: geluid.</p><div class="footnotes"><hr><ol><li id="fn:wwise">Wwise is een omgeving waarin interactieve audio kan worden ontwikkeld voor games. <a href="#fnref:wwise" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:fmod">FMOD is een omgeving waarin interactieve audio kan worden ontwikkeld voor games. <a href="#fnref:fmod" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:wwise-sdk">Wwise Software Development Kit. <a href="#fnref:wwise-sdk" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:shared-lib">Een shared library − ookwel dynamic library genoemd − wordt niet mee gecompiled in de executable, maar blijft een losstaand bestand en kan runtime worden ingeladen. Op Linux en OSX systemen zijn shared libraries te herkennen door hun <code>.so</code> extensie, op Windows is dat <code>.dll</code>. <a href="#fnref:shared-lib" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:ade">Android Development Environment is een plugin voor Eclipse. Voordat Android Studio tijdens de Google I/O in 2013 werd gepresenteerd, was dit de officiële manier van ontwikkelen voor Android. <a href="#fnref:ade" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:android-sdk">Android Software Development Kit. <a href="#fnref:android-sdk" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:android-ndk">Android Native Development Kit. <a href="#fnref:android-ndk" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:env-var">Een environment variabele is een systeem-brede variabele. De manier waarop zo’n type variabele kan worden gedeclareerd verschilt per platform. Op Windows kan dat via <code>Win + R</code>, daar intypen <code>SystemPropertiesAdvanced</code> en dan klikken op <em>Environment Variables</em>. Op OSX en Linux kan dat met het <code>export</code> commando, die je permanent kan maken door het toe te voegen aan je <code>~/.bash_profile</code> bestand. Het kan dat dit bestand nog niet bestaat. <a href="#fnref:env-var" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:gradle">Gradle is een systeem waarmee het bouwen van software kan worden geautomatiseerd. Gradle wordt meegeleverd met Android Studio. <a href="#fnref:gradle" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:cmake">CMake is een zogenaamd meta-buildsystem. Dat houdt in dat CMake de code niet zélf compileert, maar afhankelijk van het platform een GNU Makefile, een Visual Studio project of een XCode project geneert (dit is niet de <a href="https://cmake.org/cmake/help/v3.8/manual/cmake-generators.7.html#makefile-generators">complete lijst</a>). Dit doet CMake aan de hand van <code>CMakeLists.txt</code> bestanden, die op een platform onafhankelijk niveau het compileerproces omschrijven. <a href="#fnref:cmake" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:singleton">Een singleton is een design pattern binnen Object Oriented Programming die maar één instantie van een bepaalde class toestaat. <a href="#fnref:singleton" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:logcat">De logcat is waar debug berichten naartoe worden gestuurd. Android Studio heeft een logcat monitor, waarmee deze berichten kunnen worden bekeken. <a href="#fnref:logcat" title="Return to article" class="reversefootnote">↩</a></li><li id="fn:fully_qualified_java_class_name">Fully Qualified (Java) Class Name is de volledige naam van een Java class, inclusief package-name. Bijvoorbeeld: <em>nl.hku.foo.ClassNaam</em>. <a href="#fnref:fully_qualified_java_class_name" title="Return to article" class="reversefootnote">↩</a></li></ol></div></div></body>
</html>