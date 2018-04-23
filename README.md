#include<iostream>
using namespace std;
    int main (){
    cout<<"\t\tLet's play Findword Puzzle Mini Game\n\n";
    
    //pendeklarasian baris matriks
    char B1[] = {'s','w','g','t','e','b','d','a','d','r','o','p','c','z','d'};
    char B2[] = {'q','m','u','n','u','i','h','a','l','b','k','t','x','z','e'};
    char B3[] = {'s','b','g','q','o','c','n','z','k','l','w','w','f','u','b'};
    char B4[] = {'d','d','q','u','e','e','n','t','h','e','q','u','i','c','k'};
    char B5[] = {'b','r','o','w','n','f','o','x','j','u','m','p','s','o','v'};
    char B6[] = {'e','r','b','w','a','h','t','y','c','i','z','p','b','e','m'};
    char B7[] = {'q','u','v','b','t','s','f','w','o','z','d','r','b','r','q'};
    char B8[] = {'j','d','m','s','k','o','c','n','d','k','s','u','e','k','o'};
    char B9[] = {'p','q','l','d','h','c','i','d','k','s','h','g','n','t','l'};
    char B10[] = {'d','p','n','w','k','s','u','c','j','d','l','a','m','s','i'};
    char B11[] = {'n','s','i','c','y','p','w','n','s','j','a','l','d','m','f'};
    char B12[] = {'b','f','h','v','i','s','m','e','o','f','m','a','k','s','j'};
    char B13[] = {'g','v','p','w','m','o','a','h','f','y','w','n','s','u','a'};
    char B14[] = {'c','r','l','l','z','a','h','m','a','d','d','i','s','t','a'};
    char B15[] = {'k','u','r','z','g','e','s','a','g','t','p','e','r','s','e'};
    
    //pendeklarasikan pointer matriks kolom yang berisi baris baris di atas
    char *X[] = {B1, B2, B3, B4, B5, B6, B7, B8, B9, B10, B11, B12, B13, B14, B15};
    
    //menampilkan matriks char
    for (int i=0;i<15;i++){
                            for(int j=0;j<15;j++){
    cout<<*(*(X+i)+j)<<"   ";
    }
    cout<<endl;
    }
    
    //LOGIC FUNGSI
    int banyakkata;
    cout<<"\nBerapa banyak kata yang akan anda cari? ";
    cin>>banyakkata;
    
    int hasil[banyakkata], hasil_akhir[banyakkata], panjang[banyakkata] , diagonal;
    char kata[banyakkata][15];
    
    for(int i=0; i<banyakkata; i++) {
        cout<<i+1<<". ";
        cin.getline(kata[i], 15);
        panjang[i]=sizeof(kata[i]);   
        }
    
    for(int m=0; m<banyakkata; m++) {
        hasil[m]=0;
        int panjang_kata = panjang[m], x=0;
        bool ada[panjang_kata], result;
       }
    for(int baris = 0 ; baris < 15 ; r++){
            for(int i=0; i<=(15-panjang_kata); i++) {
                for(int j=i; j<=i+(panjang_kata-1); j++) {
                    if(*(*(X+baris)+j) == kata[m][x]) ada[x] = 1;
                    else ada[x] = 0;
                    x++;
                }
                for(int k=0; k<panjang_kata; k++) {
                    if(ada[k]==1) {
                        result = 1;
                        hasil[m]+=result;
                    }
                else {
                    result = 0;
                    break;
                    }
                    if(hasil[m]==panjang_kata) { 
                        hasil_akhir[m]=1; 
                        goto next; 
                    }
                }
                hasil[m]=0;
                x=0;
            }
        }

        for(int kolom = 0 ; kolom < 15 ; kolom++){
            for(int i=0; i<=(15-panjang_kata); i++) {
                for(int j=i; j<=i+(panjang_kata-1); j++) {
                    if(*(*(X+j)+kolom) == kata[m][x]) ada[x] = 1;
                    else ada[x] = 0;
                    x++;
                }
                for(int k=0; k<panjang_kata; k++) {
                    if(ada[k]==1) {
                        result = 1;
                        hasil[m]+=result;
                    }
                else {
                result = 0;
                    break;
                    }
                    if(hasil[m]==panjang_kata) { 
                        hasil_akhir[m]=1; 
                        goto next; 
                    }
                }
                hasil[m]=0;
                x=0;
            }
        }
        
     for(int diag1 = 0 ; diag1 < 15 ; diag1++){
            for(int i=0; i<=(15-panjang_kata); i++) {
            diagonal=-1;
                for(int j=i; j<=i+(panjang_kata-1); j++) {
                    ++dgnl;
                    if(*(*(X+j)+dn+dgnl) == kata[m][x]) ada[x] = 1;
                    else ada[x] = 0;
                    x++;
                }
                for(int k=0; k<panjang_kata; k++) {
                    if(ada[k]==1) {
                        result = 1;
                        hasil[m]+=result;
                    }
                    else {
                        result = 0;
                        break;
                    }
                    if(hasil[m]==panjang_kata) { 
                        hasil_akhir[m]=1; 
                        goto next; 
                    }
                }
                hasil[m]=0;
                x=0;
            }
        }

        for(int diag2 = 14 ; diag2 >= 0 ; diag--){
            for(int i=0; i<=(15-panjang_kata); i++) {
            diagonal=-1;
                for(int j=i; j<=i+(panjang_kata-1); j++) {
                    ++dgnl;
                    if(*(*(X+j)+dr-dgnl) == kata[m][x]) ada[x] = 1;
                    else ada[x] = 0;
                    x++;
                }
                for(int k=0; k<panjang_kata; k++) {
                    if(ada[k]==1) {
                        result = 1;
                        hasil[m]+=result;
                    }
                else {
                        result = 0;
                        break;
                    }
                if(hasil[m]==panjang_kata) { 
                        hasil_akhir[m]=1; 
                        goto next; 
                    }
                }
        next:
        x=0;
    }

    cout<<endl<<"Hasil : "<<endl;
    for(int i=0; i<banyakkata; i++) {
        if(hasil_akhir[i==1)
        {
            cout<<i1<<". Found!\n";
        }
        else cout<<i1<<". Not Found!\n";
    }
    return 0;
    }
