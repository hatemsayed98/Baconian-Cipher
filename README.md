# Baconian-Cipher
#include<bits/stdc++.h>
using namespace std;
int main()
{
cout<<"what do you like to do? "<<endl;
cout<<"1- Cipher a message"<<endl;
cout<<"2- Decipher a message"<<endl;
cout<<"3- End "<<endl;
    int x ,en  ,an,ln ,lol,c,in,sum=0,mp;
    bool bFail,test=1,n=1,m=1;
    string msg,arr,fin,dec,imp,las,msg1,dec1;
    while (true){
    do{
        cout<<"Please choose 1 or 2 or 3: "<<endl;
        cin>>x;

        bFail = cin.fail();
        cin.clear();
        cin.ignore (numeric_limits<streamsize>::max(), '\n');
    }while (bFail == true) ;

    while ((x!=1)&&(x!=2)&&(x!=3)){
        cout<<"Please choose 1 or 2 or 3: "<<endl;
        cin>>x;
        }
    if (x == 1)
    {
        arr="";
        fin="";
        msg="";
        cout<<"Enter your message :" <<endl;
        getline(cin,msg1);
        for(int i=0; i < msg1.length();i++){
            if(msg1[i]==' ')
                continue;
            else
                msg+=msg1[i];}

        fin="";
        for(int i=0 ; i <msg.length() ; i++){
            en= int(msg[i])  ;
            if ((en <123) &&(en>96)){
                    arr="";
               an=en-97;
               while (arr.size()<5){
                if ((an)%2==1){
                    arr=  "b" + arr  ;
                    an=an/2;
                }
                else if ((an)%2==0){
                    arr= "a"+arr  ;
                    an=an/2;
                }
               }
            fin=fin+arr;
            arr="";
            arr.erase(0,5);
               }
            else if ((en<91) && (en>64)){
                    arr="";
                an=en-65;
                while(arr.size()<5){
                if ((an)%2==1){
                    arr=  "b" + arr  ;
                    an=an/2;
                }
                else if ((an)%2==0){
                    arr= "a"+arr  ;
                    an=an/2;
                }
                }
                fin=fin+arr;
                arr="";
            }
            else cout<<endl<<"Only Letters will be encrypted";{
        }
        }
        arr.erase(0,arr.length());
        cout<<fin<<endl;
            }
            else if (x==2){
                    while((n== 1) || (m==1)){
                            n=1;
                            m=0;
                            las="";
                            dec="";
                    cout<<"Enter the encrypted message : " <<endl;

                    getline(cin,dec1);
                for(int i=0; i < dec1.length();i++){
                if(dec1[i]==' ')
                    continue;
                else
                    dec+=dec1[i];}

                    while (true){
                        if (dec.length()%5 ==0)
                            {
                            n=0;
                    }
                    for (int w=0 ; w <dec.length() ; w++){
                            if (( int (dec[w])!= 65)&& (int (dec[w])!= 66) && (int (dec[w])!=97)&&(int (dec[w])!=98)){
                                    m=1;
                            }
                }
                break;
            }
                    }
                    las="";
                    sum=0;
                    imp="";
                    n=1;
                    m=1;
                    for(int i=0;i<dec.length();i++)
                    dec[i]=tolower(dec[i]);
                for(int mp=0; mp <dec.length() ; mp=mp+5){
                        for(int k =mp ; k<mp+5 ; k++){
                            imp=imp+dec[k];
                        }
                        //las="";
                    if(int(imp[4])== 97)
                        sum=sum+ 0;
                    else if (int (imp[4])==98)
                        sum=sum +1;
                    imp=imp.erase(4,1);
                    if(int(imp[3])== 97)
                        sum=sum+ 0;
                    else if (int (imp[3])==98)
                        sum=sum + 2;
                    imp=imp.erase(3,1);
                    if(int(imp[2])== 97)
                        sum=sum+ 0;
                    else if (int (imp[2])==98)
                        sum=sum +4;
                    imp=imp.erase(2,1);
                    if(int(imp[1])== 97)
                        sum=sum+ 0;
                    else if (int (imp[1])==98)
                        sum=sum +8;
                    imp=imp.erase(1,1);
                    if(int(imp[0])== 97)
                        sum=sum+ 0;
                    else if (int (imp[0])==98)
                        sum=sum +16;
                    imp=imp.erase(0,1);
                    las=las +char(sum+97);
                    sum=0;
                    imp="";
                        }
                        cout<<endl<<las<<endl;
                        }
                        else if (x==3)
                            break;
    }
    cout<<"Thank you for using our program"<<endl;
return 0;
}
