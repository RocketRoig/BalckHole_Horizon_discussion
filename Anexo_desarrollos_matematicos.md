# Anexo de trabajo: desarrollos matematicos implicitos

Este documento no forma parte del paper. Es una guia de lectura para seguir los pasos matematicos que el articulo usa de forma compacta.

La idea central es comparar dos tiempos o condiciones:

1. El tiempo externo en el que el objeto compacto se evapora.
2. El posible cruce de una trayectoria causal exterior con la frontera gravitacional.

El "foton magico" no es una senal fisica que salga del horizonte. Es una herramienta mental: representa la trayectoria entrante mas rapida permitida por la causalidad. Si ni siquiera esa trayectoria alcanza la frontera antes de la evaporacion, ninguna particula masiva exterior puede hacerlo.

## 1. Balance energetico externo

Se parte de un volumen de control asintotico. Dentro se deposita una masa total inicial:

```math
M_{\mathrm{Bondi}}(0)=M_0.
```

El balance externo se escribe como:

```math
M_{\mathrm{ADM}}
=
M_{\mathrm{Bondi}}(u)
+
\frac{E_{\mathrm{rad}}(u)}{c^2}.
```

Donde:

- \(M_{\mathrm{ADM}}\) es la masa total conservada vista desde el infinito espacial.
- \(M_{\mathrm{Bondi}}(u)\) es la masa gravitante que queda asociada al objeto compacto.
- \(E_{\mathrm{rad}}(u)\) es la energia radiada hacia el exterior hasta el tiempo retardo \(u\).

La evaporacion completa idealizada significa:

```math
M_{\mathrm{Bondi}}(u)\to 0
\quad
\text{cuando}
\quad
u\to T_{\mathrm{evap}}.
```

En palabras: al final, la energia que se habia puesto en el volumen de control vuelve al exterior como radiacion.

## 2. Tiempo de evaporacion de Hawking

Para un agujero negro no cargado y no rotante, la escala semiclásica usual de evaporacion es:

```math
T_{\mathrm{evap}}
=
\frac{5120\pi G^2 M_0^3}{\hbar c^4}.
```

Lo importante para el argumento no es el valor numerico, sino que para una masa inicial finita \(M_0\), este tiempo es finito:

```math
M_0<\infty
\quad\Longrightarrow\quad
T_{\mathrm{evap}}<\infty.
```

Esta es la primera mitad del contraste: el reloj externo asigna una duracion finita a la evaporacion.

## 3. Aproximacion Schwarzschild: cruce externo infinito

En el capitulo conservador del paper se congela la masa y se usa Schwarzschild. Esto no describe un objeto evaporante, pero permite ver la intuicion clasica.

La metrica es:

```math
ds^2
=
-
\left(1-\frac{r_s}{r}\right)c^2dt^2
+
\left(1-\frac{r_s}{r}\right)^{-1}dr^2
+
r^2d\Omega^2,
```

con

```math
r_s=\frac{2GM_0}{c^2}.
```

Para una trayectoria radial nula:

```math
ds^2=0,
\qquad
d\Omega=0.
```

Sustituyendo:

```math
0
=
-
\left(1-\frac{r_s}{r}\right)c^2dt^2
+
\left(1-\frac{r_s}{r}\right)^{-1}dr^2.
```

Pasamos el primer termino al otro lado:

```math
\left(1-\frac{r_s}{r}\right)c^2dt^2
=
\left(1-\frac{r_s}{r}\right)^{-1}dr^2.
```

Multiplicando por \(\left(1-r_s/r\right)\):

```math
\left(1-\frac{r_s}{r}\right)^2 c^2dt^2
=
dr^2.
```

Tomando raiz:

```math
\frac{dr}{dt}
=
\pm c\left(1-\frac{r_s}{r}\right).
```

La rama entrante tiene signo negativo:

```math
\frac{dr}{dt}
=
-
c\left(1-\frac{r_s}{r}\right).
```

Entonces:

```math
dt
=
-
\frac{dr}{c(1-r_s/r)}.
```

Como:

```math
1-\frac{r_s}{r}
=
\frac{r-r_s}{r},
```

queda:

```math
dt
=
-
\frac{r\,dr}{c(r-r_s)}.
```

Escribimos:

```math
\frac{r}{r-r_s}
=
1+\frac{r_s}{r-r_s}.
```

Por tanto:

```math
dt
=
-
\frac{1}{c}
\left(
1+\frac{r_s}{r-r_s}
\right)dr.
```

Integramos desde \(r_0\) hasta \(r\), con \(r<r_0\):

```math
t(r)-t_0
=
\frac{1}{c}
\left[
r_0-r
+
r_s\ln\left(\frac{r_0-r_s}{r-r_s}\right)
\right].
```

Cuando \(r\to r_s^+\), el denominador \(r-r_s\to0^+\). Por eso:

```math
\ln\left(\frac{r_0-r_s}{r-r_s}\right)\to\infty.
```

Luego:

```math
\lim_{r\to r_s^+}\left[t(r)-t_0\right]=\infty.
```

Resultado de esta aproximacion:

```math
T_{\mathrm{cruce}}^{(\mathrm{Schw})}=\infty.
```

Como:

```math
T_{\mathrm{evap}}<\infty,
```

la comparacion formal da:

```math
T_{\mathrm{evap}}
<
T_{\mathrm{cruce}}^{(\mathrm{Schw})}.
```

Lectura: en esta aproximacion estatica, la descripcion externa nunca contiene el cruce del radio \(r_s\). Si se combina esta lectura con evaporacion finita, para el observador externo la curvatura asociada a la masa inicial ya ha radiado antes de que aparezca un cruce externo.

## 4. Por que Schwarzschild no basta

Schwarzschild tiene masa constante:

```math
M=M_0.
```

Por eso:

```math
\frac{dM}{dt}=0.
```

Pero la evaporacion exige:

```math
\frac{dM}{du}<0.
```

Asi que Schwarzschild sirve como calculo preliminar, pero no puede ser el modelo final. El siguiente paso es usar una geometria donde la masa exterior cambie dentro de la propia metrica.

## 5. Ley efectiva de perdida de masa

En el modelo dinamico se usa:

```math
\frac{dM}{du}
=
-
\frac{\alpha}{M^2},
```

con:

```math
\alpha=
\frac{\hbar c^4}{15360\pi G^2}.
```

Resolvemos:

```math
M^2\,dM=-\alpha\,du.
```

Integramos:

```math
\int_{M_0}^{M(u)} M^2\,dM
=
-
\alpha\int_0^u du.
```

Entonces:

```math
\frac{M(u)^3-M_0^3}{3}
=
-
\alpha u.
```

Por tanto:

```math
M(u)^3
=
M_0^3-3\alpha u.
```

La evaporacion completa ocurre cuando \(M(T_{\mathrm{evap}})=0\):

```math
0
=
M_0^3-3\alpha T_{\mathrm{evap}}.
```

Luego:

```math
T_{\mathrm{evap}}
=
\frac{M_0^3}{3\alpha}.
```

Sustituyendo \(\alpha\):

```math
T_{\mathrm{evap}}
=
\frac{5120\pi G^2 M_0^3}{\hbar c^4}.
```

Y la masa queda:

```math
M(u)
=
M_0
\left(
1-\frac{u}{T_{\mathrm{evap}}}
\right)^{1/3}.
```

## 6. Radio aparente dinamico

Se define:

```math
r_h(u)
=
\frac{2GM(u)}{c^2}.
```

Como \(M(u)\) decrece:

```math
\frac{dM}{du}<0,
```

tambien decrece:

```math
\frac{dr_h}{du}
=
\frac{2G}{c^2}\frac{dM}{du}
<0.
```

Definimos:

```math
k(u)
=
-
\frac{dr_h}{du}
>0.
```

Lectura: \(k(u)\) mide cuanto retrocede el horizonte aparente por unidad de tiempo retardo externo \(u\).

## 7. Metrica de Vaidya saliente

La metrica usada es:

```math
ds^2
=
-
\left(
1-\frac{2GM(u)}{c^2r}
\right)c^2du^2
-2c\,du\,dr
+r^2d\Omega^2.
```

Definimos:

```math
f(u,r)
=
1-\frac{r_h(u)}{r}.
```

Entonces:

```math
ds^2
=
-
f(u,r)c^2du^2
-2c\,du\,dr
+r^2d\Omega^2.
```

El horizonte aparente se ubica donde:

```math
f(u,r)=0.
```

Esto ocurre en:

```math
r=r_h(u).
```

## 8. Trayectoria masiva radial

Para una particula masiva radial:

```math
d\Omega=0,
\qquad
ds^2=-c^2d\tau^2.
```

Sustituimos en Vaidya:

```math
-c^2d\tau^2
=
-
f(u,r)c^2du^2
-2c\,du\,dr.
```

Dividimos por \(-c^2d\tau^2\):

```math
1
=
f(u,r)
\left(\frac{du}{d\tau}\right)^2
+
\frac{2}{c}
\frac{du}{d\tau}
\frac{dr}{d\tau}.
```

Definimos:

```math
U=\frac{du}{d\tau}.
```

Como:

```math
\frac{dr}{d\tau}
=
\frac{dr}{du}\frac{du}{d\tau}
=
U\frac{dr}{du},
```

queda:

```math
1
=
f(u,r)U^2
+
\frac{2}{c}U^2\frac{dr}{du}.
```

Despejamos:

```math
\frac{2}{c}U^2\frac{dr}{du}
=
1-f(u,r)U^2.
```

Dividimos por \(U^2\):

```math
\frac{2}{c}\frac{dr}{du}
=
\frac{1}{U^2}-f(u,r).
```

Por tanto:

```math
\frac{dr}{du}
=
\frac{c}{2}
\left[
\frac{1}{U^2}
-
f(u,r)
\right].
```

Como una particula masiva tiene \(U\) finito y:

```math
\frac{1}{U^2}>0,
```

entonces:

```math
\frac{dr}{du}
>
-
\frac{c}{2}f(u,r).
```

Esta desigualdad significa que una particula masiva no puede caer hacia radios menores mas rapido que la trayectoria nula entrante.

## 9. Trayectoria nula entrante

Para un foton radial:

```math
ds^2=0,
\qquad
d\Omega=0.
```

Entonces:

```math
0
=
-
f(u,r)c^2du^2
-2c\,du\,dr.
```

Si \(du\neq0\), dividimos por \(c\,du^2\):

```math
0
=
-
f(u,r)c
-2\frac{dr}{du}.
```

Despejamos:

```math
\left(\frac{dr}{du}\right)_{\mathrm{null}}
=
-
\frac{c}{2}f(u,r).
```

Usando \(f(u,r)=1-r_h(u)/r\):

```math
\left(\frac{dr}{du}\right)_{\mathrm{null}}
=
-
\frac{c}{2}
\left(
1-\frac{r_h(u)}{r}
\right).
```

Esta es la ecuacion del foton magico.

## 10. Separacion respecto al horizonte aparente

Definimos:

```math
\Delta(u)
=
r_p(u)-r_h(u).
```

Donde:

- \(r_p(u)\) es la posicion radial de la particula o foton.
- \(r_h(u)\) es el radio del horizonte aparente.

Si:

```math
\Delta(u)>0,
```

la trayectoria esta fuera.

Si:

```math
\Delta(u)=0,
```

habria cruce aparente.

Derivando:

```math
\frac{d\Delta}{du}
=
\frac{dr_p}{du}
-
\frac{dr_h}{du}.
```

Como:

```math
k(u)=-\frac{dr_h}{du},
```

se tiene:

```math
-\frac{dr_h}{du}=k(u).
```

Asi:

```math
\frac{d\Delta}{du}
=
\frac{dr_p}{du}
+
k(u).
```

## 11. Evolucion de Delta para el foton magico

Para el foton:

```math
\frac{dr_p}{du}
=
-
\frac{c}{2}
\left(
1-\frac{r_h(u)}{r_p(u)}
\right).
```

Como:

```math
r_p(u)=r_h(u)+\Delta(u),
```

entonces:

```math
1-\frac{r_h(u)}{r_p(u)}
=
1-\frac{r_h(u)}{r_h(u)+\Delta(u)}.
```

Llevamos a denominador comun:

```math
1-\frac{r_h}{r_h+\Delta}
=
\frac{r_h+\Delta-r_h}{r_h+\Delta}
=
\frac{\Delta}{r_h+\Delta}.
```

Por tanto:

```math
\frac{dr_p}{du}
=
-
\frac{c}{2}
\frac{\Delta(u)}{r_h(u)+\Delta(u)}.
```

Como:

```math
\frac{d\Delta}{du}
=
\frac{dr_p}{du}
+
k(u),
```

queda:

```math
\left(
\frac{d\Delta}{du}
\right)_{\mathrm{null}}
=
k(u)
-
\frac{c}{2}
\frac{\Delta(u)}{r_h(u)+\Delta(u)}.
```

Esta es la ecuacion clave.

## 12. Evaluacion en la frontera de cruce

En un cruce:

```math
\Delta=0.
```

Sustituimos en la ecuacion del foton:

```math
\left.
\left(
\frac{d\Delta}{du}
\right)_{\mathrm{null}}
\right|_{\Delta=0}
=
k(u)
-
\frac{c}{2}
\frac{0}{r_h(u)+0}.
```

El segundo termino vale cero:

```math
\left.
\left(
\frac{d\Delta}{du}
\right)_{\mathrm{null}}
\right|_{\Delta=0}
=
k(u).
```

Como el objeto evapora:

```math
k(u)>0.
```

Luego:

```math
\left.
\left(
\frac{d\Delta}{du}
\right)_{\mathrm{null}}
\right|_{\Delta=0}
>0.
```

Lectura: justo en la frontera, la separacion no esta disminuyendo hacia valores negativos; esta aumentando hacia valores positivos.

## 13. Por que esto impide el primer cruce

Supongamos que la trayectoria empieza fuera:

```math
\Delta(0)>0.
```

Para que exista un primer cruce en \(u_c\), tendria que cumplirse:

```math
\Delta(u_c)=0,
\qquad
\Delta(u)>0
\quad
\text{para}
\quad
u<u_c.
```

Si una funcion positiva llega por primera vez a cero, en ese punto no puede estar aumentando. Debe llegar con:

```math
\left.\frac{d\Delta}{du}\right|_{u_c}\leq0.
```

Pero la ecuacion del foton da:

```math
\left.\frac{d\Delta}{du}\right|_{u_c}
=
k(u_c)>0.
```

Contradiccion.

Por tanto:

```math
\Delta(0)>0
\quad\Longrightarrow\quad
\nexists\,u_c<T_{\mathrm{evap}}
\text{ tal que }
\Delta(u_c)=0.
```

## 14. Extension a particulas masivas

Para particulas masivas:

```math
\frac{dr_p}{du}
>
-
\frac{c}{2}f(u,r_p).
```

Por el mismo razonamiento:

```math
\frac{d\Delta}{du}
>
k(u)
-
\frac{c}{2}
\frac{\Delta(u)}{r_h(u)+\Delta(u)}.
```

En \(\Delta=0\):

```math
\left.
\frac{d\Delta}{du}
\right|_{\Delta=0}
>
k(u)>0.
```

La conclusion para particulas masivas es aun mas fuerte: si el foton magico no cruza, una particula masiva tampoco.

## 15. Resumen logico del paper

El paper sigue esta cadena:

```math
T_{\mathrm{evap}}<\infty
```

Schwarzschild congelado:

```math
T_{\mathrm{cruce}}^{(\mathrm{Schw})}=\infty.
```

Luego:

```math
T_{\mathrm{evap}}
<
T_{\mathrm{cruce}}^{(\mathrm{Schw})}.
```

Pero Schwarzschild no incluye evaporacion. Por eso se pasa a Vaidya:

```math
M=M(u),
\qquad
r_h=r_h(u).
```

En Vaidya:

```math
\left.
\left(
\frac{d\Delta}{du}
\right)_{\mathrm{null}}
\right|_{\Delta=0}
=
k(u)>0.
```

Y por tanto:

```math
\Delta(0)>0
\quad\Longrightarrow\quad
\nexists\,u_c<T_{\mathrm{evap}}
\text{ con }
r_p(u_c)=r_h(u_c).
```

Conclusion de trabajo:

> En el modelo evaporante, el horizonte aparente retrocede antes de ser alcanzado por cualquier trayectoria causal exterior futura.

## 16. Puntos donde conviene ser prudente

Este anexo explica los pasos usados, pero no convierte el modelo en una teoria completa. Los puntos delicados son:

- Vaidya representa radiacion nula clasica, mientras que Hawking es un fenomeno cuantico.
- El horizonte aparente no es automaticamente un horizonte de eventos global.
- La evaporacion completa con \(M\to0\) es una idealizacion efectiva.
- La retroaccion semiclásica real podria modificar la geometria cerca del final.
- El argumento prueba no cruce del horizonte aparente en este modelo, no una solucion final del problema de informacion.
