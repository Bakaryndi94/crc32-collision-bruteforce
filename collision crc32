#import de la biobliothèque permettant de hacher
import zlib

combinaison = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"

cible = zlib.crc32(b"abcd")

#fonction qui incrémente un caratère avec le suivant dans une chaine donnée
def incrementer(chaine, alphabet):
    if chaine == "":  #si la chaine est vide on prend le premier élement de combinaison
        return alphabet[0]
    dernier = chaine[-1] #on prend le dernier caractère du mot entré en paramètre
    position = alphabet.index(dernier) # on prend l'indice de l'element dans la variable dernier
    if position + 1 < len(alphabet):
        return chaine[:-1] + alphabet[position + 1] # on prend tout les éléments de la chaine sauf le dernier et on rajoute celui qui suit le dernier
    return incrementer(chaine[:-1], alphabet) + alphabet[0] #on prend tout les élements sauf le dernier et on ajoute le premier de la chaine donne en paramètre

mot = ""

#on compare avec le hash de référence avec la chaine créé jusqu'a trouver une collision jusqu'a trouver une collsion
while True:
    mot = incrementer(mot, combinaison)
    h = zlib.crc32(mot.encode())
    print(mot)
    if h == cible:
        print("Trouvé")
        print("mot de référence: abcd")
        print("collision avec la chaine :", mot)
        print("crc32 de abcd :", hex(cible))
        print("crc32 trouvé :", hex(h))
        break
