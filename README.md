# Abstract
Lahiyə 2D Unity simulyasiyasıdır. Alınmağa çalışılan nəticə maşınların Neural network istfadə edərək hər dəfə getdiyi yolu öyrənməsi və onlara verilən yolu tamamlaması idi. Maşınlar sadəcə alqoritm tərəfindən idarə olunmalı, divara dəyərsə oyundan çıxmalı, geridən gələn maşın əgər yolu tamamlayarsa, oyun bitməlidir.

# Simulyasiya
Maşınlar divarlara və ya yolun hər hansı digər maneələrinə toxunmadan yolu keçməlidirlər. Avtomobildə müəyyən istiqamətdə maneələrə qədər olan məsafəni ölçən beş sensor var. Bu sensorların oxuduği datalar avtomobilin neural networkün giriş datalarıdır. Hər bir sensor təqribən 90 dərəcə ön tərəfi əhatə edən fərqli istiqamətə işarə edir. Neural networkdən çıxan data avtomobilin dönmə gücünü müəyyən edir.

# Neural network.
İstifadə olunan neural network standart, tam əlaqəlidir. Network, 4 təbəqədən ibarətdir: 5 nöqtəli giriş, 4 və 3 nöqtəli iki təbəqə və 2 nöqtəli çıxış qatı.

<img width="435" alt="image" src="https://user-images.githubusercontent.com/86208821/202951722-c354e1cf-06a5-42c4-9d69-0472f1d8bd2d.png">
Şəbəkənin görüşünü. (Yaşıl xətlər mümkün variantları, Qırmızılar isə ya şərtlər ödənilmədiyinə görə yada ümumiyyətlə mümkünsüz variantları göstərir.) Canlı simulyasiyada ən öndə olan maşın hansıdırsa, onun neural şəbəkəsi vizual formada göstərilir.

# Neural networkün öyrənməsi alqoritmi.
Şəbəkənin öyrənməsi üçün computer science-da “genetic algorithm” adlanan alqoritmdən istfadə olunub. Alqotirmi təbiətdəki “natural selection”a oxşatmaq olar. İlk gedişlərdə N sayda maşın yaranır. Sonra maşınlar sensorlarından istfadə edərək sürətlərini tənzimləyə-tənzimləyə irəliləyirlər. Digər maşınlara nisbətən daha uğurlu (daha irəliyə gedən) maşınlar, bir sonrakı gedişdə birləşdirilir. Beləcə daha uğurlu “valideyn” maşınlardan uğurlu “övlad maşın alınır”. Hər gedişdə maşınlar bu formada birləşir, bəzən fərqli yolları seçən maşınlar da birləşə bilir, belə olduqda artıq fərqli ssenarilərə öyrəşən “təkamül etmiş” maşınlar alırıq.

# Proyektin kodunun izahı.
Genetic alqoritmin mütləq declare olunmalı dəyişən və operatorları var. Dəyişənlər sırası ilə :
currentPopulation – mövcud maşın sayı 
intermediatePopulation – birləşən maşınların sayı
newPopulation – yeni maşın sayı (birləşmədən sonra)

Operatorlar:
Selection – uğurlu olan valideynlərin seçilməsi
Recombination – uğurlu olan valideynlərin birləşdirilməsi
Mutation – fərqli yolları gedib uğurlu olan valideynlərdən əmələ gələn mutasiya olmuş maşın
PopulationCounter – mövcud nəsillərin sayı
SortPopulation – uğursuz nəsillər uğurlular ilə birləşməsin deyə nəsillərin sort olunması
