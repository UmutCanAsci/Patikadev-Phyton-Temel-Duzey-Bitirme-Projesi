# Patikadev-Phyton-Temel-Duzey-Bitirme-Projesi

1- Bir listeyi düzleştiren (flatten) fonksiyon yazın. Elemanları birden çok katmanlı listelerden ([[3],2] gibi) oluşabileceği gibi, non-scalar verilerden de oluşabilir. Örnek olarak:

input: [[1,'a',['cat'],2],[[[3]],'dog'],4,5]
output: [1,'a','cat',2,3,'dog',4,5]

ÇÖZÜM:
def flatten(liste):
    flatten_list = []
    for e in liste:
        if isinstance(e,list):
            flatten_list.extend(flatten(e))
        else:
            flatten_list.append(e)
    return flatten_list
ÖRNEK:
meyveler = ["elma",["armut",["muz",["çilek",["karpuz"]]]]]
a = flatten(meyveler)
print(a)
ÇIKTI : ['elma', 'armut', 'muz', 'çilek', 'karpuz']

2- Verilen listenin içindeki elemanları tersine döndüren bir fonksiyon yazın. Eğer listenin içindeki elemanlar da liste içeriyorsa onların elemanlarını da tersine döndürün. Örnek olarak:

input: [[1, 2], [3, 4], [5, 6, 7]]
output: [[[7, 6, 5], [4, 3], [2, 1]]
ÇÖZÜM
def reverse(liste):
    liste.reverse()
    
    for i in range(len(liste)):
        if isinstance(liste[i], list):
            liste[i] = reverse(liste[i])  # recursive çağrı
    
    return liste

ÖRNEK
sayılar = [1, 2, [3, [4, 5, 6], 7, 8, [9]]]
b = reverse(sayılar)
print(b)
ÇIKTI: [[[9], 8, 7, [6, 5, 4], 3], 2, 1]
