
# Proyectos de Prolog

## Ejercicio 1: Suma de Números

Este ejercicio incluye un predicado para sumar dos números.

% Predicado para sumar dos números 
suma(X, Y, Z) :- Z is X + Y.

% Predicados de prueba 
prueba_suma :- 
 suma(5, 3, Resultado), 
 write('5 + 3 = '), write(Resultado), 
 nl.

% Ejecutar la prueba 
:- prueba_suma.

## Ejercicio 2: Manipulación de Listas

Este ejercicio incluye un predicado para invertir una lista.

% Predicado para invertir una lista 
invertir([], []). 
invertir([Cabeza|Cola], ListaInvertida) :- 
 invertir(Cola, ListaAuxiliar), 
 append(ListaAuxiliar, [Cabeza], ListaInvertida).

% Predicados de prueba 
prueba_invertir :- 
 invertir([1, 2, 3, 4, 5], ListaResultado), 
 write('Lista original: [1, 2, 3, 4, 5]'), 
 nl, 
 write('Lista invertida: '), write(ListaResultado), 
 nl.

% Ejecutar la prueba 
:- prueba_invertir.

## Ejercicio 3: Diagnóstico (Código Prolog Adicional)

Este ejercicio incluye un sistema básico de diagnóstico médico en Prolog que determina posibles enfermedades basadas en síntomas.


% Las Reglas
gripe(X) :- malestar(X), fiebre(X), tos(X), sec_nas(X).
dengue(X) :- malestar(X), fiebre(X), dolorartmus(X), rash(X).
influenza(X) :- malestar(X), fiebre(X), tos(X), dolor_muscular(X).
covid19(X) :- malestar(X), fiebre(X), tos(X), dificultad_respiratoria(X).
alergia(X) :- estornudos(X), picorojos(X), secnas(X).

% El diagnóstico 
diagnostico(X) :- nl, write('Se investiga GRIPE'), gripe(X),
                  nl, write(X), write(' tiene sintomas de GRIPE.'), fail.
diagnostico(X) :- nl, write('Se investiga DENGUE'), dengue(X),
                  nl, write(X), write(' tiene sospecha de DENGUE.'), fail.
diagnostico(X) :- nl, write('Se investiga INFLUENZA'), influenza(X),
                  nl, write(X), write(' tiene sospecha de INFLUENZA.'), fail.
diagnostico(X) :- nl, write('Se investiga COVID-19'), covid19(X),
                  nl, write(X), write(' tiene sospecha de COVID-19.'), fail.
diagnostico(X) :- nl, write('Se investiga ALERGIA'), alergia(X),
                  nl, write(X), write(' tiene sospecha de ALERGIA.'), fail.
diagnostico(X) :- write(' NO SE LOGRO UN DIAGNOSTICO.').

% Ejemplo de consultas
% Consulta 1
% ?- diagnostico(pepe).


      git clone https://github.com/tu_usuario/proyectos_prolog.git
   cd proyectos_prolog
   
      git checkout -b suma_numeros
   
      git add suma_numeros.pl
   git commit -m "Agregar código del ejercicio de suma"
   git push origin suma_numeros
