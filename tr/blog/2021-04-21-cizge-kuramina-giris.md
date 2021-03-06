Merhaba arkadaşlar, bu yazımda sizlerle graf teorisi hakkında konuşacağım.

Şimdi sizlerle örnek bir grafa göz atalım.

![](../resimler/cizge_kuramina_giris/1.jpeg)

Şimdi bu graf, matematik dilinde nasıl gösterilir ona bakalım.

*G, Yönelimsiz Graf(Undirected Graph) olmak üzere;*

G = (V, E)

V = {a, b, c, d, e}

E = {(a, c), (a, b), (c, b), (b, e), (b, d)}

Şimdi burada G, V ve E nedir bunu inceleyelim.

G, tanımını yaptığımız graf [Graph]

V, graftaki düğümler(node) [Vertex]

E, graftaki düğümlerin birbiriyle yaptığı bağların kümesi [Edge]

![](../resimler/cizge_kuramina_giris/2.jpeg)

Bu arada yukarıdaki resimdeki tanımları da açıklamadan geçemeyeceğim.

$$e= (v_1, v_2) \in E$$

**$$\begin{align*}v_1\end{align*}$$ and $$\begin{align*}v_2\end{align*}$$ are adjacent**

Gördüğünüz üzere, V kümesinde a, b, c, d, e nodeları var. E deki elemanlara bakalım

(a, c) a ile c arasında bir bağlantı vardır. (*$$v_1$$ and $$v_2$$ are adjacent* tanımda bu cümle geçmeseydi sadece a dan c ye bir bağlantı vardır diyebilirdik. c den a ya bir bağlantı vardır diyemezdik.)

(a, b) a ile b arasında bir bağlantı vardır.

(c, b) c ile b arasında bir bağlantı vardır.

(b, e) b ile e arasında bir bağlantı vardır.

(b, d) b ile d arasında bir bağlantı vardır.

# Yönelimli Graflar(Directed Graph)

![](../resimler/cizge_kuramina_giris/3.jpeg)

Bu resmi açıklayalım.
$$
\begin{align*}
& a=(v_1 , v_2)
\end{align*}
$$

$$v_1$$ : origin node of a

$$v_2$$ : terminating node of a

Yani sadece $$v_1$$ düğümünden $$v_2$$ düğümüne bir bağlantı vardır diyebiliriz. $$v_2$$ den $$v_1$$ e bir bağlantı olduğunu söyleyemeyiz.

Aşağıda örnek bir Yönelimli Graf var.

![](../resimler/cizge_kuramina_giris/4.jpeg)

$$
\begin{align*}
& D = (V, A) \\

& V = {a, b, c, d}\\

& A = {(a, b), (b, a), (a, c), (c, b), (a, d)} \\
\end{align*}
$$

$$(a, b)$$ $$a$$ dan $$b$$ ye bir bağlantı vardır.

$$(b, a)$$ $$b$$ den $$a$$ ya bir bağlantı vardır.

$$(a, c)$$ $$a$$ dan $$c$$ ye bir bağlantı vardır.

$$(c, b)$$ $$c$$ den $$b$$ ye bir bağlantı vardır.

$$(a, d)$$ $$a$$ dan $$d$$ ye bir bağlantı vardır.

Buradan gördüğünüz gibi $$d$$ den $$a$$ ya bağlantı olması için $$A$$ kümesi içinde $$(d, a)$$ da olmak zorundaydı.

# Ağırlıklı Graflar(Weighted Graphs)

Eğer bir graphın kenarları belli bir değeri de içinde taşıyorsa(nasıl bir tanım yaptım ben de bilmiyorum ama örnek verince anlatmaya çalıştığım şey çok iyi anlaşılacaktır diye düşünüyorum.)

Bu grafa ağırlıklı graf denir. Bu ağırlık değerleri *cost, length distance, delay, probabilty vs.* olabilir. Bir örnek verelim:

Uşak - Ankara arası 15km
Ankara-İstanbul arası 27km
İstanbul-Malatya arası 78km
Malatya-Uşak arası 80km
Malatya-Ankara arası 51km
Uşak-İstanbul arası 62km

Çizeceğimiz grafta
Uşak'ı U
Ankara'yı A
İstanbul'u İ
Malatya'yı M
olarak gösterelim.

![](../resimler/cizge_kuramina_giris/5.jpeg)

# Multigraphs

$$e_1$$, $$a$$ düğümünden $$b$$ düğümüne giden bir edge olsun.

Eğer $$a$$ düğümünden $$b$$ düğümüne giden birden fazla edge varsa, biz bu edge'e *parallel edge* deriz.

Eğer bir düğümden yine aynı düğüme giden bir edge varsa biz buna *loop* deriz.

plain graph: loop ve parallel edge içermeyen graflara denir.

multigraph: plain graph olmayan grafa denir.

![](../resimler/cizge_kuramina_giris/6.jpeg)

# Komşuluk Matrixi (Adjacent Matrix)

![](../resimler/cizge_kuramina_giris/7.jpeg)

yukarıdaki resim için konuşalım.

$$A$$ resimde gösterdiğimiz komşuluk matrixidir.

$$A_1,_2 = 1$$ olduğu için $$v_1$$ den $$v_2$$ ye bir edge vardır. $$A_2,_1 = 1$$  olduğu için $$v_2$$ den $$v_1$$ ye de edge vardır. Yani hem $$v_1$$ den $$v_2$$ ye gidilebilir hem de $$v_2$$ den $$v_1$$ e gidilebilir.

![](../resimler/cizge_kuramina_giris/8.jpeg)

yukarıdaki resim için konuşalım.

$$A$$ resimde gösterdiğimiz komşuluk matrixidir.

$$A_1,_2 = 1$$ olduğu için $$v_1$$ den $$v_2$$ ye bir edge vardır. Ama $$A_2, _1 = 0$$  olduğu için $$v_2$$ den $$v_1$$ edge yoktur. Yani $$v_1$$ den $$v_2$$ ye gidilebilir ama $$v_2$$ den $$v_1$$ e gidilemez.

![](../resimler/cizge_kuramina_giris/9.jpeg)
