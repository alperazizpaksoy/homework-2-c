# homework-2-c
#include <stdio.h>
#include <stdlib.h>
int binarySearch(int dizi[], int l, int r, int aranan) {
    if(r >= l) {
        int ortasi = l + (r - l) / 2;
        if(dizi[ortasi] == aranan) {
            return ortasi;
        }
        if(dizi[ortasi] > aranan) {
            return binarySearch(dizi, l, ortasi - 1, aranan);
        }
        return binarySearch(dizi, ortasi + 1, r, aranan);
    }
    else 
    return -1;
}
int main(int argc, char *argv[]) {
	int dizi[] = {3, 4, 8, 9, 24, 47, 68, 76, 84};
    int n = 9;
    int aranan ;
    printf("Aramak istediginiz elemani giriniz. \n");
    scanf("%d",&aranan);
    int sonuc = binarySearch(dizi, 0, n-1, aranan);
    if(sonuc == -1) {
        printf("%d elemani dizide bulunamadi.\n", aranan);
    }
    else {
        printf("%d elemani dizinin %d. elemanidir. \n", aranan, sonuc+1);
    }
	return 0;
}
