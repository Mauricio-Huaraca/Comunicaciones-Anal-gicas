# Comunicaciones-Anal-gicas
% Modulación AM en MATLAB
clc, clear all, close all;
Am = 1; 
fm = 10; 
Ac = 1; 
fc = 100; 
ka = 0.7; % Índice de modulación (menor a 1)

Fs = 5000; % Frecuencia de muestreo 
t = 0:1/Fs:0.2; % tiempo vectorial

m = Am * sin(2* pi* fm*t);

c = Ac * cos(2* pi* fc*t);

s = Ac .* (1 + ka .*m) .*cos(2* pi* fc.*t);

% Cifras gráficas;
figure(1)
subplot(3,1,1) 
plot(t, m, 'b') 
title('Señal de Mensaje m(t)') 
xlabel('Tiempo (s)') 
ylabel('Amplitud') 
grid on

subplot(3,1,2) 
plot(t, c, 'r')
title('Señal Portadora c(t)')
xlabel('Tiempo (s)') 
ylabel('Amplitud') 
grid on

subplot(3,1,3) 
plot(t, s, 'k') 
title('Señal Modulada AM') 
xlabel('Tiempo (s)') 
ylabel('Amplitud') 
