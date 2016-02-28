fn="new.txt"
function newGrep(){
read -p "What are you looking for? " someFile
cat $fn | grep -n  " "$someFile"/"
 }
function regexGrep(){ cat $fn | grep -n "t[wo]o"; }

function driver() {
while true; do
        echo "a: regex grep"
        echo "b: space slash grep"
        read -p "Which grep you tryna do? " ab
        case $ab in
                [Aa]* ) regexGrep; break;;
                [Bb]* ) newGrep; break;;
                * ) echo "Please answer a or b.";;
        esac
done;
}
