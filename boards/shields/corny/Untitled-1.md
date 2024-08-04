Il problema, potrebbe essere collegato al fatto che ci sono tanti file al interno della cartella e ha difficoltà quando fa il listing…
ho lanciato un LS tipo 5 min fa e sta ancora bloccato.
Per me bisogna entrare nella cartella e organizzare/archiviare questi file. Per esempio, creare una o più sottocartelle e spostare dei file vecchi… Sempre se questo fosse possibile.
Quanti file sono dentro questa cartella?    /var/www/html/remida/report/files



Say hello To my little Friend. Say Hello To My Little Friend>

As dori Sa Impartasesc cu Tine Si E
As Dori Sa Impartesesc 
As Dori Sa Impartasesc totul cu tine 
As Dori Sa ImpartasecS

Hello Say hello to My little Friend mac2016! 
Questo Pdo pero questo periodo del anno! 
Hello to



 
 




#include <dt-bindings/zmk/keys.h>
#include <behaviors.dtsi>

#define MO_TOG(layer) &mo_tog layer layer   // Macro to apply momentary-layer-on-hold/toggle-layer-on-tap to a specific layer

/ {
    behaviors {
        mo_tog: behavior_mo_tog {
            compatible = "zmk,behavior-hold-tap";
            label = "mo_tog";
            #binding-cells = <2>;
            flavor = "hold-preferred";
            tapping-term-ms = <200>;
            bindings = <&mo>, <&tog>;
        };
    };

    keymap {
        compatible = "zmk,keymap";
        default_layer {
            bindings = <
                &mo_tog 2 1     // &mo 2 on hold, &tog 1 on tap
                MO_TOG(3)       // &mo 3 on hold, &tog 3 on tap
            >;
        };
    };
};