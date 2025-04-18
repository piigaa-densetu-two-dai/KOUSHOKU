# ～ PC-6001 好色アダプター ～
![好色アダプター](/koushoku.jpg)  
好色アダプターはNEC PC-6001mk2/PC-6601専用のVGAアップスキャンコンバーターです。  
15色モード、滲みカラーに対応します。  
PC-6001mk2SR/PC-6601SRには対応していません。PC-6001mk2/PC-6601以外に接続すると壊れます絶対に接続しないで下さい。  
personal use only  

# ファームウェア
koushoku-640x480.uf2 (640x480モード31kHz/60Hz用スキャンライン付き)  
koushoku-640x400.uf2 (640x400モード31kHz/70Hz用スキャンライン付き)  
640x400モードはモニターにより相性が出やすいと思います。  

# ファームウェア書き込み方法
RaspberryPiPicoボードの動作確認を兼ねて組立前に書込みを行なう事をお勧めします。  
RaspberryPiPicoボードをボード上のBOOTSELボタンを押しながらPCとUSB接続して下さい。  
接続が成功するとドライブが認識されます。  
認識されたドライブに上記のファームウェアの何れかをドラッグアンドドロップ(コピー)します。  
ドライブが見えなくなったら書込み完了。  

# 部品リスト
J1 02x04 IDCヘッダー  
J2 DB15 VGAコネクター  
R1 2k  
R2 1k  
R3 510  
R4 2k  
R5 1k  
R6 510  
R7 2k  
R8 1k  
R9 510  
SW1 タクトスイッチ  
U1 RaspberryPiPico  

# DINプラグとフラットケーブルの結線方法(半田付け難易度高いです)
同じ番号同士を接続して下さい。8から1の順に半田付けするのが良いです。DINプラグの樹脂部分は熱で溶けやすいので手早く半田付けして下さい。  
![DIN](/DIN.png)![ケーブル](/cable.jpg)  

# 使用方法
DINプラグをPC-6001mk2/PC-6601のRGB出力、VGAコネクタにVGAモニター、RaspberryPiPicoボードのUSBコネクタにUSB電源を接続するだけです。  

# カラーモード切替方法
COLOUR MODEボタンを押す毎に以下の順でカラーモードが循環します。  
15色モード(デフォルト)  
滲み着色モード(マゼンタ/緑/滲み少)  
滲み着色モード(マゼンタ/緑/滲み多)  
滲み着色モード(緑/マゼンタ/滲み少)  
滲み着色モード(緑/マゼンタ/滲み多)  
滲み着色モード(オレンジ/シアン/滲み少)  
滲み着色モード(オレンジ/シアン/滲み多)  
滲み着色モード(シアン/オレンジ/滲み少)  
滲み着色モード(シアン/オレンジ/滲み多)  

# ご注意 回路を簡素にする為に信号電圧レベル変換回路を省略しています
RP2040のIOピン(プラス側にダイオードが入っていないピンのみ)をRGB出力端子に直結しています。  
実質的に問題ないであろう事を確認していますが定格外の使い方をしているのでその辺自己責任でお願いします。  
