# Cartoonstrike-Fly
You can fly in cartoonstrike
var mc7,
    tBJ,
    up = true;

function defineMc7() {
    mc7 = Main.children[7];

    if(mc7.s38 === null) setTimeout(defineMc7, 50);
    else tBJ = mc7.s38.b33.tBJ;
}
defineMc7();

function fly(e) {
    var state = (e.type == "keydown") ?true: false;

    if(e.code == "KeyW") up = state;

    if(up) {
        tBJ.gravMass = -1;

        mc7.s38.I32 = "jump__in";
    }
    if(!up) {
        tBJ.gravMass = 2;
         mc7.s38.I32 = "idle";
    }
}
window.addEventListener("keydown", fly);
window.addEventListener("keyup", fly);
