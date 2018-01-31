## kitekintés

- svm: könyvekben azért van sok, mert matematikailag jól leírható, ezért több bizonyítható tulajdonsága van
- ha interpretálás fontos, nem feltétlen gbm-t választana, vagy ha 100.000-nél kevesebb adatpont.
- több 100.000 adatpont, bináris klasszifikáció: erre tuti a gbm a legjobb

## gbm

- Adaboost: döntési fák átlaga. Iteratívan történik a fák megtanulása. Felsúlyozzuk a rosszult prediktált adatpontokat, majd ezt ismételni.
- gbm: hasonló az alapja, máshogy megy a súlyozás, új fa keresés
- sok paraméter, h2o implementáció legfontosabbjai:
ntrees, max depth, learn rate, nfolds, stooping rounds, stopping metric, stopping tolerance
- minden gbm könyvtár tud random forestet is
- kicsit jobb, mint a random forest, de lényegesen több időt kell eltölteni a paraméter tuningolással
- lehet overfitting, random forestnél ez kb lehetetlen
- h2o gbm tuning tutorial for R
- xgboost, h2o, lightgbm a legjobb implementációk, mindhez van R és Python interface is.
- sparkon csak lassabb, mert különböző coreok között sokat kell kommunikálni, sőt, egy gépen több proci sem éri meg hasonló okok miatt. persze ez mind függ az adatmérettől
- [benchmark](https://github.com/szilard/GBM-multicore)

### packages

- gbm: one core, easy install, oldest, now not relevant
- xgboost: easy install
- LightGBM: only easily available on Linux :(, amúgy leggyorsabb
- h2o: lassabb, de productionbe könnyebb menni

## misc

- shrinkage: overfitting elkerülő csillapítási faktor
