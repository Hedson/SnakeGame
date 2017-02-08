//---------------------------------------------------------------------------

#include <vcl.h>
#pragma hdrstop
#include <iostream>
#include <cstdlib>  //  2 biblioteki dla generatora liczb pseudolosowych
#include <ctime>    //

#include "mmsystem.h"   // biblioteka do wczytania muzyki
#include "Unit1.h"
//---------------------------------------------------------------------------
#pragma package(smart_init)
#pragma resource "*.dfm"
TForm1 *Form1;

TImage *czlony_weza[1000];

int x = 0;
int y = 0;

int dlugosc1 = 1;


bool kolizja( TImage * glowa, TImage * plansza)
        {

            if( glowa->Left <= plansza->Left-10 ||         //lewo
                glowa->Left >= plansza->Left + plansza->Width - 30 ||      //prawo
                glowa->Top <= plansza->Top-10 ||                       //gora
                glowa->Top >= plansza->Top + plansza->Height - 30 )      //dol
                {
                        return true;
                }
                else
                {
                        return false;
                }

        }

bool kolizja_waz( TImage * glowa, TImage * czlon)       // kolizja z czlonami weza
        {

                if( glowa->Left >= czlon->Left-10 && //left
                    glowa->Left <= czlon->Left+czlon->Width-10 &&  //right
                    glowa->Top  >= czlon->Top-10  &&
                    glowa->Top  <= czlon->Top+czlon->Height-10
                  )
                        return true;

                else
                        return false;

        }


bool jedzenie( TImage * glowa, TImage * jablko)
        {

                if( glowa->Left >= jablko->Left-30 && //left
                    glowa->Left <= jablko->Left+jablko->Width-20 &&  //right
                    glowa->Top  >= jablko->Top-30  &&
                    glowa->Top  <= jablko->Top+jablko->Height-20
                  )
                        return true;

                else
                        return false;


        }

int losuj_x()
        {
                srand( time( NULL ) );
                int liczba =( std::rand() % 951 ) + 500;
                return liczba;
        }

int losuj_y()
        {
                srand( time( NULL ) );
                int liczba =( std::rand() % 751 ) + 50;
                return liczba;
        }

//---------------------------------------------------------------------------
__fastcall TForm1::TForm1(TComponent* Owner)
        : TForm(Owner)
{
}
//---------------------------------------------------------------------------


void __fastcall TForm1::FormKeyDown(TObject *Sender, WORD &Key,
      TShiftState Shift)
{
   if(Key == VK_LEFT)
   {
        left->Enabled = true;
        right->Enabled = false;
        up->Enabled = false;
        down->Enabled = false;
   }

   if(Key == VK_RIGHT)
   {
        left->Enabled = false;
        right->Enabled = true;
        up->Enabled = false;
        down->Enabled = false;
   }

   if(Key == VK_UP)
   {
        left->Enabled = false;
        right->Enabled = false;
        up->Enabled = true;
        down->Enabled = false;
   }

   if(Key == VK_DOWN)
   {
        left->Enabled = false;
        right->Enabled = false;
        up->Enabled = false;
        down->Enabled = true;
   }

}
//---------------------------------------------------------------------------
/*void __fastcall TForm1::FormKeyUp(TObject *Sender, WORD &Key,
      TShiftState Shift)
{
   if(Key == VK_LEFT)     left->Enabled = false;
   if(Key == VK_RIGHT)    right->Enabled = false;
   if(Key == VK_UP)       up->Enabled = false;
   if(Key == VK_DOWN)     down->Enabled = false;
}    */
//---------------------------------------------------------------------------
void __fastcall TForm1::upTimer(TObject *Sender)
{

        for(int i = dlugosc1-2; i>=0; i--)
        {
                if(czlony_weza[i]->Visible==true)
                {
                czlony_weza[i+1]->Top = czlony_weza[i]->Top ;
                czlony_weza[i+1]->Left = czlony_weza[i]->Left ;
                czlony_weza[i+1]->Visible==true;
                }
        }
        czlony_weza[0]->Top-=50;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::downTimer(TObject *Sender)
{


         for(int i = dlugosc1-2; i>=0; i--)
        {
                if(czlony_weza[i+1]->Visible==true)
                {
                czlony_weza[i+1]->Top = czlony_weza[i]->Top;
                czlony_weza[i+1]->Left = czlony_weza[i]->Left ;
                czlony_weza[i+1]->Visible==true;
                }
        }
        czlony_weza[0]->Top+=50;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::rightTimer(TObject *Sender)
{


         for(int i = dlugosc1-2; i>=0; i--)
        {
                if(czlony_weza[i+1]->Visible==true)
                {
                czlony_weza[i+1]->Top = czlony_weza[i]->Top ;
                czlony_weza[i+1]->Left = czlony_weza[i]->Left ;
                czlony_weza[i+1]->Visible==true;
                }
        }
        czlony_weza[0]->Left+=50;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::leftTimer(TObject *Sender)
{


         for(int i = dlugosc1-2; i>=0; i--)
        {
                if(czlony_weza[i+1]->Visible==true)
                {
                czlony_weza[i+1]->Top = czlony_weza[i]->Top ;
                czlony_weza[i+1]->Left = czlony_weza[i]->Left ;
                czlony_weza[i+1]->Visible==true;
                }
        }
        czlony_weza[0]->Left-=50;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::checkTimer(TObject *Sender)
{
    if(kolizja(czlony_weza[0],plansza) == true)
     {
        left->Enabled = false;
        right->Enabled = false;
        up->Enabled = false;
        down->Enabled = false;
        Label1->Caption="KONIEC GRY - PRZEGRALES";
        Label1->Visible=true;
        Button1->Visible=true;
     }

   for(int i = dlugosc1-1; i>0; i--)
   {
     if(kolizja_waz(czlony_weza[0],czlony_weza[i]))
     {
        left->Enabled = false;
        right->Enabled = false;
        up->Enabled = false;
        down->Enabled = false;
        Label1->Caption="KONIEC GRY - PRZEGRALES";
        Label1->Visible=true;
        Button1->Visible=true;
        text_tail->Caption="Zajdles swoj ogon,\nbardzo sie starales\n lecz z gry wyleciales";
        text_tail->Visible=true;
     }
   }



     length_window->Caption=IntToStr(dlugosc1);


     if(jedzenie(czlony_weza[0],jablko)==true && jablko->Visible==true)
     {


        jablko->Visible=false;
        Sleep(100);
        dlugosc1++;
        length_window->Caption=IntToStr(dlugosc1);

        // tu trzeba wstawic cos by powiekszac weza o 1 czlon.
        if(left->Enabled==true)
        {
                czlony_weza[dlugosc1-1] = new TImage(Form1);
                czlony_weza[dlugosc1-1]->Left = czlony_weza[dlugosc1-2]->Left + 50;
                czlony_weza[dlugosc1-1]->Top = czlony_weza[dlugosc1-2]->Top;
                czlony_weza[dlugosc1-1]->Width = 50;  // potrzebne?
                czlony_weza[dlugosc1-1]->Height = 50; // jw.
                czlony_weza[dlugosc1-1]->Picture->LoadFromFile("img/czlon2.bmp");
                czlony_weza[dlugosc1-1]->Parent=Form1;
                czlony_weza[dlugosc1-1]->Visible=1;
        }
        if(right->Enabled==true)
        {
                czlony_weza[dlugosc1-1] = new TImage(Form1);
                czlony_weza[dlugosc1-1]->Left = czlony_weza[dlugosc1-2]->Left -50;
                czlony_weza[dlugosc1-1]->Top = czlony_weza[dlugosc1-2]->Top;
                czlony_weza[dlugosc1-1]->Width = 50;  // potrzebne?
                czlony_weza[dlugosc1-1]->Height = 50; // jw.
                czlony_weza[dlugosc1-1]->Picture->LoadFromFile("img/czlon2.bmp");
                czlony_weza[dlugosc1-1]->Parent=Form1;
                czlony_weza[dlugosc1-1]->Visible=1;
        }
        if(up->Enabled==true)
        {
                czlony_weza[dlugosc1-1] = new TImage(Form1);
                czlony_weza[dlugosc1-1]->Left = czlony_weza[dlugosc1-2]->Left;
                czlony_weza[dlugosc1-1]->Top = czlony_weza[dlugosc1-2]->Top + 50;
                czlony_weza[dlugosc1-1]->Width = 50;  // potrzebne?
                czlony_weza[dlugosc1-1]->Height = 50; // jw.
                czlony_weza[dlugosc1-1]->Picture->LoadFromFile("img/czlon2.bmp");
                czlony_weza[dlugosc1-1]->Parent=Form1;
                czlony_weza[dlugosc1-1]->Visible=1;
        }
        if(down->Enabled==true)
        {
                czlony_weza[dlugosc1-1] = new TImage(Form1);
                czlony_weza[dlugosc1-1]->Left = czlony_weza[dlugosc1-2]->Left;
                czlony_weza[dlugosc1-1]->Top = czlony_weza[dlugosc1-2]->Top - 50;
                czlony_weza[dlugosc1-1]->Width = 50;  // potrzebne?
                czlony_weza[dlugosc1-1]->Height = 50; // jw.
                czlony_weza[dlugosc1-1]->Picture->LoadFromFile("img/czlon2.bmp");
                czlony_weza[dlugosc1-1]->Parent=Form1;
                czlony_weza[dlugosc1-1]->Visible=1;
        }





        jablko->Left=losuj_x();
        jablko->Top=losuj_y();
        jablko->Visible=true;
     }

}
//---------------------------------------------------------------------------


void __fastcall TForm1::Button1Click(TObject *Sender)
{
      Button1->Visible=false;
      Label1->Visible=false;
      text_tail->Visible=false;
      czlony_weza[0]->Top=450;
      czlony_weza[0]->Left=550;
      jablko->Visible=true;
      for(int i = dlugosc1-2; i>=0; i--)
        {
                czlony_weza[i+1]->Visible=0;
        }
      dlugosc1 =  1;
}
//---------------------------------------------------------------------------

void __fastcall TForm1::FormCreate(TObject *Sender)
{
       czlony_weza[0] = new TImage(Form1);
       czlony_weza[0]->Left = 550;
       czlony_weza[0]->Top = 450;
       czlony_weza[0]->Width = 50;  // potrzebne?
       czlony_weza[0]->Height = 50; // jw.
       czlony_weza[0]->Picture->LoadFromFile("img/czlon.bmp");
       czlony_weza[0]->Parent=Form1;
       czlony_weza[0]->Visible=1;
       sndPlaySound("snd/lion_king.wav", SND_ASYNC);
}
//---------------------------------------------------------------------------

