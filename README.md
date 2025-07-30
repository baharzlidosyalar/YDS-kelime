# YDS-kelime
YDS de çıkması muhtemel kelimeleri öğretmeyi amaçlar
kelimeler = {
    "abandon": "terk etmek",
    "abstract": "soyut",
    "acquire": "edinmek, kazanmak",
    "adapt": "uyum sağlamak",
    "adequate": "yeterli",
    "adjacent": "bitisik, yanındaki",
    "advocate": "savunmak",
    "affect": "etkilemek",
    "allocate": "tahsis etmek",
    "alter": "değiştirmek",
    "ambiguous": "belirsiz",
    "analyse": "analiz etmek",
    "annual": "yıllık",
    "apparent": "bariz, açık",
    "appropriate": "uygun",
    "approximate": "yaklaşık",
    "arbitrary": "rastgele",
    "assess": "değerlendirmek",
    "assign": "görevlendirmek",
    "assist": "yardım etmek",
    "assume": "varsaymak",
    "attain": "ulaşmak",
    "attribute": "özellik, bağlamak",
    "authorize": "yetki vermek",
    "available": "mevcut",
    "bias": "önyargı",
    "brief": "kısa, öz",
    "capable": "yetenekli",
    "cease": "durdurmak",
    "clarify": "açıklamak",
    "coherent": "tutarlı",
    "commence": "başlamak",
    "compatible": "uyumlu",
    "compensate": "telafi etmek",
    "comprehensive": "kapsamlı",
    "conclude": "sonuçlandırmak",
    "concrete": "somut",
    "confirm": "doğrulamak",
    "consequence": "sonuç",
    "considerable": "önemli",
    "consist": "oluşmak",
    "constitute": "oluşturmak",
    "constrain": "zorlamak",
    "consult": "danışmak",
    "consume": "tüketmek",
    "contrast": "karşılaştırmak",
    "contribute": "katkıda bulunmak",
    "conventional": "geleneksel",
    "convey": "iletmek",
    "convince": "ikna etmek",
    "cooperate": "iş birliği yapmak",
    "coordinate": "koordine etmek",
    "core": "öz, çekirdek",
    "criteria": "ölçüt",
    "crucial": "çok önemli",
    "debate": "tartışma",
    "decline": "azalmak",
    "deduce": "sonuç çıkarmak",
    "define": "tanımlamak",
    "demonstrate": "göstermek",
    "derive": "türetmek",
    "design": "tasarlamak",
    "detect": "tespit etmek",
    "deviate": "sapmak",
    "device": "cihaz",
    "devote": "adamak",
    "dimension": "boyut",
    "discrete": "ayrı",
    "displace": "yerinden etmek",
    "display": "sergilemek",
    "dispose": "elden çıkarmak",
    "distinct": "farklı",
    "distribute": "dağıtmak",
    "diverse": "çeşitli",
    "document": "belge",
    "dominate": "hakim olmak",
    "duration": "süre",
    "eliminate": "elemek",
    "emerge": "ortaya çıkmak",
    "emphasis": "vurgulama",
    "enable": "olanak sağlamak",
    "encounter": "karşılaşmak",
    "enhance": "arttırmak",
    "ensure": "garanti etmek",
    "entity": "varlık",
    "equate": "eşit tutmak",
    "estimate": "tahmin etmek",
    "evaluate": "değerlendirmek",
    "evident": "apaçık",
    "exclude": "dışlamak",
    "expand": "genişletmek",
    "expert": "uzman",
    "explicit": "açık",
    "exploit": "faydalanmak",
    "expose": "maruz bırakmak",
    "external": "dış",
    "facilitate": "kolaylaştırmak",
    "factor": "etken",
    "feature": "özellik",
    "finance": "finans",
    "fluctuate": "dalgalanmak",
    "focus": "odaklanmak",
    "framework": "çerçeve",
    "fundamental": "temel",
    "function": "işlev",
    "generate": "üretmek",
    "global": "küresel",
    "grade": "not",
    "guarantee": "garanti",
    "highlight": "vurgulamak",
    "identify": "tanımlamak",
    "ignore": "görmezden gelmek",
    "impact": "etki",
    "implement": "uygulamak",
    "imply": "anlamına gelmek",
    "incentive": "teşvik"
}

import random

def oyun(kelimeler):
    kelime_listesi = list(kelimeler.items())
    yanlislar = {}

    while kelime_listesi:
        kelime, anlam = random.choice(kelime_listesi)
        cevap = input(f"'Karının Programına Hoşgeldin !! {kelime}' kelimesinin anlamı nedir? ").strip().lower()

        dogru_cevaplar = [anlam, anlam.split(",")[0]]  # Eğer birden fazla anlam varsa ilkini de kabul et

        if cevap in dogru_cevaplar:
            print("Doğru Serdar Bey! ✔\n")
            kelime_listesi.remove((kelime, anlam))
        else:
            print(f"Yanlışşş cevap karısının gülü ! Doğru cevap: {anlam}\n")
            yanlislar[kelime] = anlam

    if yanlislar:
        print("Yanlış bildiğin kelimeler tekrar sorulacak.\n")
        return yanlislar
    else:
        print("Tebrikler, tüm kelimeleri bildin! 🎉")
        return None

yanlislar = kelimeler
while yanlislar:
    yanlislar = oyun(yanlislar)
