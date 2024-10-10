<!DOCTYPE html>
<html lang="de">

<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta charset="utf-8">
    <title>Startseite</title>
    <link rel="stylesheet" href="Startseite.css">
    <link rel="stylesheet" href="Startseite-Inhalt.css">
</head>

<body>

    
    <div id="Haupt-Kasten">






        
        <div id="Haupt-Navigationsleiste">
            
            <div id="Logo-Kasten">
                

            </div>




           
            <div id="Option-Button">
                
                <button id="menuButton"></button>

            </div>


        </div>

       
        <div id="Scroll-roller">

            <div id="Startbild">   

            </div>

            <div id="Starttext">   

                <h4>Beginne dein Workouts mit unseren Produkten</h4>
                Wir haben die besten Produkte für deine effektiven Training. 

            </div>

            <div id="Startbild1">   

            </div>

            <div id="Starttext1">   
                <h4>Beginne dein Workouts mit unseren Produkten</h4>
                Wir haben die besten Produkte für deine effektiven Training. 
            </div>

            <div id="Startbild2">   

            </div>

            <div id="Starttext2">   
                <h4>Beginne dein Workouts mit unseren Produkten</h4>
                Wir haben die besten Produkte für deine effektiven Training. 
            </div>




        </div>

        <div id="navigationsleiste">
            <div id="Icons_Box">
                
                <a href="https://www.deinshop.de">
                    <div id="Startseite-Box">
                        <button id="Startseite-Button"></button>
                   
                        <h4 class="Text">&nbsp;Startseite</h4>
                    

                    </div>   
                </a>


         
                
                <a href="https://www.deinshop.de">
                    <div id="Shop-Box">
                        <button id="Shop-Button"></button>
                        <h4 id="Shop-Text" style="color: white;">&nbsp;Shop</h4>
                    </div>
                </a>

                <a href="https://www.deinshop.de">
                    <div id="Kundendienst-Box">
                        <button id="Kundendienst-Button"></button>
                       
                        <h4 id="Kundendienst-Text">&nbsp;Kundendienst</h4>
                        
    
                    </div>  
                </a>

                <a href="https://www.deinshop.de">

                    <div id="Vergleich-Box">

                        <button id="Vergleich-Button"></button>

                        <h4 id="Vergleich-Text" style="color: white;">&nbsp;Vergleichen</h4>

                    </div>

                </a>




            </div>    
        </div>



    </div>
 
        <!-- Button, um die Navigationsleiste anzuzeigen -->
        

        <!-- Navigationsleiste -->



    <script>
        const menuButton = document.getElementById('menuButton');
        const navigationsleiste = document.getElementById('navigationsleiste');

        menuButton.addEventListener('click', function () {
            if (navigationsleiste.classList.contains('aktiv')) {
                navigationsleiste.classList.remove('aktiv'); // Navigationsleiste zusammenrollen
                
                // Nach einer kurzen Verzögerung (um die Animation abzuschließen) ausblenden
                setTimeout(() => {
                    navigationsleiste.style.display = 'none'; // Leiste ausblenden
                }, 300); // Die Zeit sollte der Dauer der Transition entsprechen
            } else {
                navigationsleiste.style.display = 'block'; // Leiste anzeigen
                setTimeout(() => {
                    navigationsleiste.classList.add('aktiv'); // Navigationsleiste entfalten
                }, 10); // Leichte Verzögerung für sanfteren Übergang
            }
        });

 // Scroll-Event-Listener hinzufügen
 document.addEventListener('scroll', function () {
            const scrollTop = window.pageYOffset || document.documentElement.scrollTop;

            // Prüfen, ob der Benutzer nach unten scrollt
            if (scrollTop > lastScrollTop) {
                // Nach unten scrollen: Leiste ausblenden
                if (navigationsleiste.classList.contains('aktiv')) {
                    navigationsleiste.classList.remove('aktiv');
                    setTimeout(() => {
                        navigationsleiste.style.display = 'none';
                    }, 300);
                }
            } else {
                // Nach oben scrollen: Leiste anzeigen
                if (!navigationsleiste.classList.contains('aktiv')) {
                    navigationsleiste.style.display = 'block'; // Leiste anzeigen
                    setTimeout(() => {
                        navigationsleiste.classList.add('aktiv'); // Navigationsleiste entfalten
                    }, 10);
                }
            }
            lastScrollTop = scrollTop; // Aktualisiere die letzte Scrollposition
        });

    </script>

<script>
    let lastScrollPosition = 0;

    document.addEventListener('scroll', function () {
        const scrollRoller = document.getElementById('Scroll-roller');
        const navigationsleiste = document.getElementById('Navigationsleiste');
        const scrollPosition = window.scrollY;
        const maxScroll = document.documentElement.scrollHeight - window.innerHeight;
        const scrollPercentage = scrollPosition / maxScroll;

        // Scroll-Roller Hintergrundfarbe ändern
        const colorValue = Math.min(Math.floor(scrollPercentage * 255), 255);
        scrollRoller.style.backgroundColor = `rgb(${255 - colorValue}, ${255 - colorValue}, ${255 - colorValue})`;

        // Navigationsleiste anzeigen, wenn nach oben gescrollt wird
        if (scrollPosition < lastScrollPosition) {
            navigationsleiste.style.transform = 'translateY(0)';
        } else {
            navigationsleiste.style.transform = 'translateY(-100%)'; // Ausblenden beim Scrollen nach unten
        }

        lastScrollPosition = scrollPosition;
    });
</script>




</body>



</html>
