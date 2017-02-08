//---------------------------------------------------------------------------

#ifndef Unit1H
#define Unit1H
//---------------------------------------------------------------------------
#include <Classes.hpp>
#include <Controls.hpp>
#include <StdCtrls.hpp>
#include <Forms.hpp>
#include <ExtCtrls.hpp>
#include <Graphics.hpp>
#include <jpeg.hpp>
#include <ImgList.hpp>
//---------------------------------------------------------------------------
class TForm1 : public TForm
{
__published:	// IDE-managed Components
        TImage *tlo;
        TTimer *down;
        TTimer *up;
        TTimer *right;
        TTimer *left;
        TLabel *Label1;
        TImage *plansza;
        TButton *Button1;
        TTimer *check;
        TImage *jablko;
        TLabel *length_window;
        TLabel *Label2;
        TLabel *text_tail;
        void __fastcall FormKeyDown(TObject *Sender, WORD &Key,
          TShiftState Shift);
        void __fastcall upTimer(TObject *Sender);
        void __fastcall downTimer(TObject *Sender);
        void __fastcall rightTimer(TObject *Sender);
        void __fastcall leftTimer(TObject *Sender);
        void __fastcall checkTimer(TObject *Sender);
        void __fastcall Button1Click(TObject *Sender);
        void __fastcall FormCreate(TObject *Sender);
private:	// User declarations
public:		// User declarations
        __fastcall TForm1(TComponent* Owner);
};
//---------------------------------------------------------------------------
extern PACKAGE TForm1 *Form1;
//---------------------------------------------------------------------------
#endif
