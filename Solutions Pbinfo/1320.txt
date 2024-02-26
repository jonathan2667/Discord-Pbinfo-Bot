#include <iostream>

using namespace std;

int main()
{
    int a[1001],n,i;
    bool cr,eg,de;
    cin>>n;
    for(i=0;i<n;++i)
        cin>>a[i];

    cr=eg=de=false;
    for(i=0;i<n-1;++i)
        if (a[i]==a[i+1])
            eg=true;   //  daca gasim doua elementele egale, acest lucru se memoreaza
        else
            if (a[i]<a[i+1])
                cr=true;   // se memoreaza gasirea a doua elemente in ordine crescatoare
            else
                de=true;  // se memoreaza gasirea a doua elemente in ordine descrescatoare
    if (cr and de)
        cout<<"sir neordonat";  // sirul neordonat are atat elemente crescatoare cat si descrescatoare
    else
        if (eg and !cr and !de)
            cout<<"sir constant";  // are elemente egale, nu are crescator, nici descrescator
        else
            if (cr and !eg and !de)  // are elemente crescatoare, nu are egal, nici descrescator
                cout<<"sir strict crescator";
            else
                if (cr and eg and !de)  // are elemente egale si descrescatoare nu are descrescator
                    cout << "sir crescator";
                else
                    if (de and eg and !cr)  // are elemente descrescatoare si egale, nu are crescator
                        cout << "sir descrescator";
                    else
                        cout << "sir strict descrescator";  // are elemente descrescatoare, nu are egale nici crescatoare
    return 0;
}
