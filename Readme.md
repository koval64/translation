
# "common"
#
# użycie taga "common" sprawia że tagi językowe są ignorowane
# czyli dopisane poniżej tagi:
#
# ...
# "pl": "Anuluj",
# "en": "Cancel"
# ...
# 
# zostaną całkowicie zignorowane.


{
  "jakas tam nazwa informacyjnie nigdzie nie uzywana":
  {
    "pragma_label": "CapitalizedLabelsWithoutSpacesRequired",
    "array_label": "UPPERCASE_STRING_WITH_UNDERLINES_REQUIRED",
    "contents": [
      "id": "UPPERCASE_REQUIRED",
      "common": " taki sobie napis"             <----- tag "common"
      "pl": "Anuluj",                           <----- zostanie zignorowane
      "en": "Cancel",                           <----- zostanie zignorowane
    ]
  }
}



#
# używanie wersji językowej czyli "pl": "Anuluj", "en": "Cancel"
#

{
  "jakas tam nazwa informacyjnie nigdzie nie uzywana":
  {
    "pragma_label": "CapitalizedLabelsWithoutSpacesRequired",
    "array_label": "UPPERCASE_STRING_WITH_UNDERLINES_REQUIRED",
    "contents": [
      "id": "UPPERCASE_REQUIRED",
      "pl": "Anuluj",                       <----- tag językowy
      "en": "Cancel"                        <----- tag językowy
    ]
  }
}


#
# używanie "underline"
#
# "pl":   "Anuluj",
# "pl_m": "------"
#
# użycie taga językowego z dopiskiem "_m" czyli maska
# oznaczające które znaki zastąpić znakami z charsetu z podkreśleniem
#
# maskować można pojedyńcze wybrany litery np.:
#
# "pl":   "Anuluj",
# "pl_m": " - - -"
#
# sprawi że litery "nlj" zostaną wyświetlone z podkreśleniem
# a litery "Auu" bez podkreślenia
#
# UWAGA:
# funkcja nie ma zabezpieczenia, więc pewnie się wywali jeśli
# string maski będzie miał więcej znaków niż string maskowany
#

{
  "jakas tam nazwa informacyjnie nigdzie nie uzywana":
  {
    "pragma_label": "CapitalizedLabelsWithoutSpacesRequired",
    "array_label": "UPPERCASE_STRING_WITH_UNDERLINES_REQUIRED",
    "contents": [
      "id": "UPPERCASE_REQUIRED",
      "pl":   "Anuluj",
      "pl_m": "------",                       <----- maska do underline
      "en": "Cancel"
    ]
  }
}



# Mnemonik "menu_opt"
# "menu_opt": "1"       # [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, < ]
#
# Znak "<" jest zamieniany na strzałkę, czyli znak powrotu z menu.
# Opcja z menu opt jest wstawiana bezpośrednio przed stringa.
#
# Strzałka jest brana z normalnego charsetu
# Cyfry są brane z charsetu +$80 ( czyli negatywu )
#



# Mnemonik "comment": "tutaj se jakiś komentarz blebleblaba"
#
# mnemoniki inne niż "menu_opt", "pl", "en", "common" i inne wymagane
# wymienione powyżej są całkowicie ignorowane i mogą posłużyć jako komentarze.


############
### BUGS ###
############
#
# definiowanie mnemoników z tekstem o długości zerowej spowoduje błąd, np:
#
# "common": "",
# "pl": "",
# "en": ""
# itp
#
# przykładowe ROZWIĄZANIE - jakikolwiek pojedynczy znak np spacja:
# lub całkowite usunięcie mnemonika
#
# "common": " "
#









