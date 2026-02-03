# Comunicaciones-Anal-gicas
Modulación AM en MATLAB
clc;
clear;
close all;

% Parámetros
Am = 1;          % Amplitud del mensaje
fm = 10;         % Frecuencia del mensaje (Hz)
Ac = 1;          % Amplitud de la portadora
fc = 100;        % Frecuencia de la portadora (Hz)
ka = 0.7;        % Índice de modulación (menor a 1)

Fs = 5000;       % Frecuencia de muestreo
t = 0:1/Fs:0.2;  % Vector tiempo

% Señal mensaje
m = Am * sin(2*pi*fm*t);

% Señal portadora
c = Ac * cos(2*pi*fc*t);

% Señal AM
s = Ac * (1 + ka.*m) .* cos(2*pi*fc.*t);

% Gráficas
figure;

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
grid on

