from tkinter import *
from tkinter.ttk import *
from math import *
from numpy import *
import matplotlib.pyplot as plt
from matplotlib.backends.backend_tkagg \
import FigureCanvasTkAgg
from tkinter.messagebox import showerror
import fontTools
import warnings
def RP3(Z1F, Z2F, Z3F, Z4F, R1F, R2F, R3F, R4F):
   global C0_3, C1_3, C2_3, C3_3
   s2=(R2F**3-R1F**3)/(Z2F-Z1F)
   s3=(R3F**3-R1F**3)/(Z3F-Z1F)
   s4=(R4F**3-R1F**3)/(Z4F-Z1F)
   s5=Z2F**2-Z3F**2+Z1F*Z2F-Z1F*Z3F
   s6=Z2F**2-Z4F**2+Z1F*Z2F-Z1F*Z4F
   k1=(s2-s3)/(Z2F-Z3F)
   k2=(s2-s4)/(Z2F-Z4F)
   k3=s5/(Z2F-Z3F)
   k4=s6/(Z2F-Z4F)
   C3_3=(k1-k2)/(k3-k4)
   C2_3=k1-C3_3*k3
   C1_3=s2-(Z2F**2+Z2F*Z1F+Z1F**2)*C3_3-(Z2F+Z1F)*C2_3
   C0_3=R1F**3-C3_3*Z1F**3-C2_3*Z1F**2-C1_3*Z1F
def RP4(Z1F, Z2F, Z3F, Z4F, Z5F, R1F, R2F, R3F, R4F, R5F):
   global C0_4, C1_4, C2_4, C3_4, C4_4
   a12=(R2F**4-R1F**4)/(Z2F-Z1F);
   a13=(R3F**4-R1F**4)/(Z3F-Z1F);
   a14=(R4F**4-R1F**4)/(Z4F-Z1F);
   a15=(R5F**4-R1F**4)/(Z5F-Z1F);
   a23=(a13-a12)/(Z3F-Z2F);
   a24=(a14-a12)/(Z4F-Z2F);
   a25=(a15-a12)/(Z5F-Z2F);
   b233=(Z3F**3-Z2F**3+Z3F**2*Z1F-Z2F**2*Z1F+Z3F*Z1F**2-Z2F*Z1F**2)/(Z3F-Z2F)
   b223=(Z3F**2-Z2F**2+Z3F*Z1F-Z2F*Z1F)/(Z3F-Z2F)
   b234=(Z4F**3-Z2F**3+Z4F**2*Z1F-Z2F**2*Z1F+Z4F*Z1F**2-Z2F*Z1F**2)/(Z4F-Z2F)
   b224=(Z4F**2-Z2F**2+Z4F*Z1F-Z2F*Z1F)/(Z4F-Z2F)
   b235=(Z5F**3-Z2F**3+Z5F**2*Z1F-Z2F**2*Z1F+Z5F*Z1F**2-Z2F*Z1F**2)/(Z5F-Z2F);
   b225=(Z5F**2-Z2F**2+Z5F*Z1F-Z2F*Z1F)/(Z5F-Z2F)
   a31=(a24-a23)/(b224-b223)
   b31=(b234-b233)/(b224-b223)
   a32=(a25-a23)/(b225-b223)
   b32=(b235-b233)/(b225-b223)
   C4_4=(a32-a31)/(b32-b31)
   C3_4=a31-C4_4*b31
   C2_4=a23-C4_4*b233-C3_4*b223
   C1_4=a12-C4_4*(Z2F**3+Z2F**2*Z1F+Z2F*Z1F**2+Z1F**3)-C3_4*(Z2F**2+Z1F*Z2F+Z1F**2)-C2_4*(Z1F+Z2F)
   C0_4=R1F**4-C4_4*Z1F**4-C3_4*Z1F**3-C2_4*Z1F**2-C1_4*Z1F
def RP5(Z1F, Z2F, Z3F, Z4F, Z5F, Z6F, R1F, R2F, R3F, R4F, R5F, R6F):
   global C0_5, C1_5, C2_5, C3_5, C4_5, C5_5
   a115=(Z1F**5-Z6F**5)/(Z1F-Z6F)-(Z5F**5-Z6F**5)/(Z5F-Z6F)
   a114=(Z1F**4-Z6F**4)/(Z1F-Z6F)-(Z5F**4-Z6F**4)/(Z5F-Z6F)
   a113=(Z1F**3-Z6F**3)/(Z1F-Z6F)-(Z5F**3-Z6F**3)/(Z5F-Z6F)
   a112=(Z1F**2-Z6F**2)/(Z1F-Z6F)-(Z5F**2-Z6F**2)/(Z5F-Z6F)
   b11=(R1F**5-R6F**5)/(Z1F-Z6F)-(R5F**5-R6F**5)/(Z5F-Z6F)
   a125=(Z2F**5-Z6F**5)/(Z2F-Z6F)-(Z5F**5-Z6F**5)/(Z5F-Z6F)
   a124=(Z2F**4-Z6F**4)/(Z2F-Z6F)-(Z5F**4-Z6F**4)/(Z5F-Z6F)
   a123=(Z2F**3-Z6F**3)/(Z2F-Z6F)-(Z5F**3-Z6F**3)/(Z5F-Z6F)
   a122=(Z2F**2-Z6F**2)/(Z2F-Z6F)-(Z5F**2-Z6F**2)/(Z5F-Z6F)
   b12=(R2F**5-R6F**5)/(Z2F-Z6F)-(R5F**5-R6F**5)/(Z5F-Z6F)
   a135=(Z3F**5-Z6F**5)/(Z3F-Z6F)-(Z5F**5-Z6F**5)/(Z5F-Z6F)
   a134=(Z3F**4-Z6F**4)/(Z3F-Z6F)-(Z5F**4-Z6F**4)/(Z5F-Z6F)
   a133=(Z3F**3-Z6F**3)/(Z3F-Z6F)-(Z5F**3-Z6F**3)/(Z5F-Z6F)
   a132=(Z3F**2-Z6F**2)/(Z3F-Z6F)-(Z5F**2-Z6F**2)/(Z5F-Z6F)
   b13=(R3F**5-R6F**5)/(Z3F-Z6F)-(R5F**5-R6F**5)/(Z5F-Z6F)
   a145=(Z4F**5-Z6F**5)/(Z4F-Z6F)-(Z5F**5-Z6F**5)/(Z5F-Z6F)
   a144=(Z4F**4-Z6F**4)/(Z4F-Z6F)-(Z5F**4-Z6F**4)/(Z5F-Z6F)
   a143=(Z4F**3-Z6F**3)/(Z4F-Z6F)-(Z5F**3-Z6F**3)/(Z5F-Z6F)
   a142=(Z4F**2-Z6F**2)/(Z4F-Z6F)-(Z5F**2-Z6F**2)/(Z5F-Z6F)
   b14=(R4F**5-R6F**5)/(Z4F-Z6F)-(R5F**5-R6F**5)/(Z5F-Z6F)
   a215=(a115/a112)-(a145/a142)
   a214=(a114/a112)-(a144/a142)
   a213=(a113/a112)-(a143/a142)
   b21=(b11/a112)-(b14/a142)
   a225=(a125/a122)-(a145/a142)
   a224=(a124/a122)-(a144/a142)
   a223=(a123/a122)-(a143/a142)
   b22=(b12/a122)-(b14/a142)
   a235=(a135/a132)-(a145/a142)
   a234=(a134/a132)-(a144/a142)
   a233=(a133/a132)-(a143/a142)
   b23=(b13/a132)-(b14/a142)
   a315=(a215/a213)-(a235/a233)
   a314=(a214/a213)-(a234/a233)
   b31=(b21/a213)-(b23/a233)
   a325=(a225/a223)-(a235/a233)
   a324=(a224/a223)-(a234/a233)
   b32=(b22/a223)-(b23/a233)
   a415=(a315/a314)-(a325/a324)
   b41=(b31/a314)-(b32/a324)
   C5_5=b41/a415
   C4_5=(b31-a315*C5_5)/a314
   C3_5=(b21-a215*C5_5-a214*C4_5)/a213
   C2_5=(b11-a115*C5_5-a114*C4_5-a113*C3_5)/a112
   C1_5=(R1F**5-R6F**5-C5_5*(Z1F**5-Z6F**5)-C4_5*(Z1F**4-Z6F**4)-C3_5*(Z1F**3-Z6F**3)-C2_5*(Z1F**2-Z6F**2))/(Z1F-Z6F)
   C0_5=R1F**5-C5_5*Z1F**5-C4_5*Z1F**4-C3_5*Z1F**3-C2_5*Z1F**2-C1_5*Z1F
def RP6(Z1F, Z2F, Z3F, Z4F, Z5F, Z6F, Z7F, R1F, R2F, R3F, R4F, R5F, R6F, R7F):
   global C0_6, C1_6, C2_6, C3_6, C4_6, C5_6, C6_6
   a116=(Z1F**6-Z7F**6)/(Z1F-Z7F)-(Z6F**6-Z7F**6)/(Z6F-Z7F)
   a115=(Z1F**5-Z7F**5)/(Z1F-Z7F)-(Z6F**5-Z7F**5)/(Z6F-Z7F)
   a114=(Z1F**4-Z7F**4)/(Z1F-Z7F)-(Z6F**4-Z7F**4)/(Z6F-Z7F)
   a113=(Z1F**3-Z7F**3)/(Z1F-Z7F)-(Z6F**3-Z7F**3)/(Z6F-Z7F)
   a112=(Z1F**2-Z7F**2)/(Z1F-Z7F)-(Z6F**2-Z7F**2)/(Z6F-Z7F)
   b11=(R1F**6-R7F**6)/(Z1F-Z7F)-(R6F**6-R7F**6)/(Z6F-Z7F)
   a126=(Z2F**6-Z7F**6)/(Z2F-Z7F)-(Z6F**6-Z7F**6)/(Z6F-Z7F)
   a125=(Z2F**5-Z7F**5)/(Z2F-Z7F)-(Z6F**5-Z7F**5)/(Z6F-Z7F)
   a124=(Z2F**4-Z7F**4)/(Z2F-Z7F)-(Z6F**4-Z7F**4)/(Z6F-Z7F)
   a123=(Z2F**3-Z7F**3)/(Z2F-Z7F)-(Z6F**3-Z7F**3)/(Z6F-Z7F)
   a122=(Z2F**2-Z7F**2)/(Z2F-Z7F)-(Z6F**2-Z7F**2)/(Z6F-Z7F)
   b12=(R2F**6-R7F**6)/(Z2F-Z7F)-(R6F**6-R7F**6)/(Z6F-Z7F)
   a136=(Z3F**6-Z7F**6)/(Z3F-Z7F)-(Z6F**6-Z7F**6)/(Z6F-Z7F)
   a135=(Z3F**5-Z7F**5)/(Z3F-Z7F)-(Z6F**5-Z7F**5)/(Z6F-Z7F)
   a134=(Z3F**4-Z7F**4)/(Z3F-Z7F)-(Z6F**4-Z7F**4)/(Z6F-Z7F)
   a133=(Z3F**3-Z7F**3)/(Z3F-Z7F)-(Z6F**3-Z7F**3)/(Z6F-Z7F)
   a132=(Z3F**2-Z7F**2)/(Z3F-Z7F)-(Z6F**2-Z7F**2)/(Z6F-Z7F)
   b13=(R3F**6-R7F**6)/(Z3F-Z7F)-(R6F**6-R7F**6)/(Z6F-Z7F)
   a146=(Z4F**6-Z7F**6)/(Z4F-Z7F)-(Z6F**6-Z7F**6)/(Z6F-Z7F)
   a145=(Z4F**5-Z7F**5)/(Z4F-Z7F)-(Z6F**5-Z7F**5)/(Z6F-Z7F)
   a144=(Z4F**4-Z7F**4)/(Z4F-Z7F)-(Z6F**4-Z7F**4)/(Z6F-Z7F)
   a143=(Z4F**3-Z7F**3)/(Z4F-Z7F)-(Z6F**3-Z7F**3)/(Z6F-Z7F)
   a142=(Z4F**2-Z7F**2)/(Z4F-Z7F)-(Z6F**2-Z7F**2)/(Z6F-Z7F)
   b14=(R4F**6-R7F**6)/(Z4F-Z7F)-(R6F**6-R7F**6)/(Z6F-Z7F)
   a156=(Z5F**6-Z7F**6)/(Z5F-Z7F)-(Z6F**6-Z7F**6)/(Z6F-Z7F)
   a155=(Z5F**5-Z7F**5)/(Z5F-Z7F)-(Z6F**5-Z7F**5)/(Z6F-Z7F)
   a154=(Z5F**4-Z7F**4)/(Z5F-Z7F)-(Z6F**4-Z7F**4)/(Z6F-Z7F)
   a153=(Z5F**3-Z7F**3)/(Z5F-Z7F)-(Z6F**3-Z7F**3)/(Z6F-Z7F)
   a152=(Z5F**2-Z7F**2)/(Z5F-Z7F)-(Z6F**2-Z7F**2)/(Z6F-Z7F)
   b15=(R5F**6-R7F**6)/(Z5F-Z7F)-(R6F**6-R7F**6)/(Z6F-Z7F)
   a216=(a116/a112)-(a156/a152)
   a215=(a115/a112)-(a155/a152)
   a214=(a114/a112)-(a154/a152)
   a213=(a113/a112)-(a153/a152)
   b21=(b11/a112)-(b15/a152)
   a226=(a126/a122)-(a156/a152)
   a225=(a125/a122)-(a155/a152)
   a224=(a124/a122)-(a154/a152)
   a223=(a123/a122)-(a153/a152)
   b22=(b12/a122)-(b15/a152)
   a236=(a136/a132)-(a156/a152)
   a235=(a135/a132)-(a155/a152)
   a234=(a134/a132)-(a154/a152)
   a233=(a133/a132)-(a153/a152)
   b23=(b13/a132)-(b15/a152)
   a246=(a146/a142)-(a156/a152)
   a245=(a145/a142)-(a155/a152)
   a244=(a144/a142)-(a154/a152)
   a243=(a143/a142)-(a153/a152)
   b24=(b14/a142)-(b15/a152)
   a316=(a216/a213)-(a246/a243)
   a315=(a215/a213)-(a245/a243)
   a314=(a214/a213)-(a244/a243)
   b31=(b21/a213)-(b24/a243)
   a326=(a226/a223)-(a246/a243)
   a325=(a225/a223)-(a245/a243)
   a324=(a224/a223)-(a244/a243)
   b32=(b22/a223)-(b24/a243)
   a336=(a236/a233)-(a246/a243)
   a335=(a235/a233)-(a245/a243)
   a334=(a234/a233)-(a244/a243)
   b33=(b23/a233)-(b24/a243)
   a416=(a316/a314)-(a336/a334)
   a415=(a315/a314)-(a335/a334)
   b41=(b31/a314)-(b33/a334)
   a426=(a326/a324)-(a336/a334)
   a425=(a325/a324)-(a335/a334)
   b42=(b32/a324)-(b33/a334)
   a516=(a416/a415)-(a426/a425)
   b51=(b41/a415)-(b42/a425)
   C6_6=b51/a516
   C5_6=(b41-a416*C6_6)/a415
   C4_6=(b31-a316*C6_6-a315*C5_6)/a314
   C3_6=(b21-a216*C6_6-a215*C5_6-a214*C4_6)/a213
   C2_6=(b11-a116*C6_6-a115*C5_6-a114*C4_6-a113*C3_6)/a112
   C1_6=(R1F**6-R7F**6-C6_6*(Z1F**6-Z7F**6)-C5_6*(Z1F**5-Z7F**5)-C4_6*(Z1F**4-Z7F**4)-C3_6*(Z1F**3-Z7F**3)-C2_6*(Z1F**2-Z7F**2))/(Z1F-Z7F)
   C0_6=R1F**6-C6_6*Z1F**6-C5_6*Z1F**5-C4_6*Z1F**4-C3_6*Z1F**3-C2_6*Z1F**2-C1_6*Z1F
def arb():
   if var_rad.get() == 1:
         Bi=0.15
         Mi=2*1.627e-27
         Zi=1.6e-19
   elif var_rad.get() == 2:
         Bi=0.18
         Mi=4*1.627e-27
         Zi=2*1.6e-19
   elif var_rad.get() == 3:
         Bi=0.19
         Mi=14*1.627e-27
         Zi=7*1.6e-19
   else:
         Bi=0.18
         Mi=16*1.627e-27
         Zi=8*1.6e-19
def Clear_Graph(event):
    NofPlots.set(0)
    ax.set_xlabel('z,m', fontname='Arial', fontsize=14)
    ax.set_ylabel('r,m', fontname='Arial', fontsize=14)
    Legend_Str.set('')
    ax.clear()
def Check_Errors(event):
    ######################  Reading Input Parameters  ######################
    global rb0, rb, Z, min_rb, Z_Focus, Point_Focus_Number, NofPoints, NofPlots, Legend_Str, rb_out_text, Zstart
    Check=1; entry5.delete(0,END)
    try:
       Uac=float(entry41.get())*1000
    except:
       Check=0
       entry5.insert(0,'Wronge value of acceleraton voltage. It is not numerical data. Pleace check input data.')
    try:
       Ib =float(entry42.get())
    except:
       Check=0
       entry5.insert(0,'Wronge value of beam current. It is not numerical data. Pleace check input data.')
    try:
       P = float(entry43.get())
    except:
       Check=0
       entry5.insert(0,'Wronge value of operation pressure. It is not numerical data. Pleace check input data.')
    try:
       rb0 =float(entry44.get())
    except:
       Check=0
       entry5.insert(0,'Wronge value of start beam radius. It is not numerical data. Pleace check input data.')
    try:
       Teta0 =radians(float(entry45.get()))
    except:
       Check=0
       entry5.insert(0,'Wronge value of start angle of beam convergence. It is not numerical data. Pleace check input data.')
    try:
       ZStart=float(entry46.get())
    except:
       Check=0
       entry5.insert(0,'Wronge value of start z coordinate. It is not numerical data. Pleace check input data.')
    try:
       ZLast=float(entry47.get())
    except:
       Check=0
       entry5.insert(0,'Wronge value of last z coordinate. It is not numerical data. Pleace check input data.')
    try:
       NofPoints=int(entry48.get())
    except:
       Check=0
       entry5.insert(0,'Wronge value of number of points. It is not numerical integer value. Pleace check input data.')
    if (Check==1):
       if ((Uac/1000>40)|(Uac/1000<5)):
          entry5.insert(0,'Wronge value of acceleration voltage. It have to be in range 5 - 40 kV. Pleace check input data.')
          Check=0
       if ((Ib>40)|(Ib<1e-4)):
          entry5.insert(0,'Wronge value of beam current. It have to be in range 1e**(-4) - 40 A. Pleace check input data.')
          Check=0
       if ((P>20)|(P<0.001)):
          entry5.insert(0,'Wronge value of operation pressure. It have to be in range 0.001 - 20 Pa. Pleace check input data.')
          Check=0
       if ((rb0<0.001)|(rb0>30)):
          entry5.insert(0,'Wronge value of start beam radius. It have to be in range 0.001 - 30 mm. Pleace check input data.')
          Check=0
       if (((degrees(Teta0)<0)|(degrees(Teta0)>20))&(Check==1)):
          entry5.insert(0,'Wronge value of start angle of beam convergence. It have to be in range 1 - 20 deg. Pleace check input data.')
          Check=0
       if ((ZStart<0.1)|(ZStart>10)):
          entry5.insert(0,'Wronge value of start z coordinate. It have to be in range 0.1 - 10 m. Pleace check input data.')
          Check=0
       if ((ZLast<=0.1)|(ZLast>20)):
          entry5.insert(0,'Wronge value of last beam z coordinate. It have to be in range 0.11 - 20 m. Pleace check input data.')
          Check=0
       if ((ZStart > ZLast)):
          entry5.insert(0,'Wronge value of start and last beam z coordinates. Start coordinate have to be smaller value, than last one. Pleace check input data.')
          Check=0
       if ((NofPoints<100)|(NofPoints>1e5)):
          entry5.insert(0,'Wronge value of number of reference points. It have to be in range from 100 to 1e7. Pleace check input data.')
          Check=0
    if (Check==1):
       eel=1.6e-19
       me=9.1e-31
       eps0=8.8542e-12
       ve=sqrt(2*eel*Uac/me)
       vez=ve*cos(Teta0)
       ver=ve*sin(Teta0)
       c=3e8
       beta_sqr=(ve/c)**2
       gamma=sqrt(1-beta_sqr)
       hshtrih=1.05e-34
       kB=1.38e-23
       T=300
       if var_rad.get() == 1:
          Mi=2*1.627e-27
          Bi=((sqrt(2*pi/Mi)))**3*(hshtrih/(sqrt(kB*T))**5)*exp(1e-15*eel*Uac/(kB*T))*1e-58
          Zi=1.6e-19
       elif var_rad.get() == 2:
         Mi=4*1.627e-27
         Bi=((sqrt(2*pi/Mi)))**3*(hshtrih/(sqrt(kB*T))**5)*exp(1e-15*eel*Uac/(kB*T))*1e-58
         Zi=2*1.6e-19
       elif var_rad.get() == 3:
         Mi=14*1.627e-27
         Bi=((sqrt(2*pi/Mi)))**3*(hshtrih/(sqrt(kB*T))**5)*exp(1e-15*eel*Uac/(kB*T))*1e-58
         Zi=7*1.6e-19
       else:
         Mi=16*1.627e-27
         Bi=((sqrt(2*pi/Mi)))**3*(hshtrih/(sqrt(kB*T))**5)*exp(1e-15*eel*Uac/(kB*T))*1e-58
         Zi=8*1.6e-19
       Z = linspace(ZStart, ZLast, NofPoints)
       dz=Z[2] - Z[1]
       Teta_Min=2*atan(1e-4*Zi**(4/3)/(2*gamma*beta_sqr))
       Teta_Max=2*atan(Zi**(1.5)/(2*gamma*beta_sqr))
       rb=[0.001*rb0]
       Teta=-Teta0
       for zl in range(1, NofPoints):
          ne=Ib/(pi*(rb[zl-1])**2)
          fr=Uac/ne
          ni0=Bi*(10-P)*ne*sqrt(pi*Mi*eps0*ne/(me*Uac))*exp(1.9e-14*Uac/(eps0*ne*(rb[zl-1])**2))
          D_Teta=sqrt(abs((8*pi*((rb[zl-1])*Zi)**2*dz*log(Teta_Min/Teta_Max))/ne))
          #print('ne=', ne, 'ni0=', ni0, 'fr=', fr, 'exp=', 2e-14*Uac/(eps0*ne*(rb[zl-1])**2))
          f=ne/(ne-ni0)
          C=Ib*(1+f-beta_sqr)/(4*pi*eps0*ve*Uac)
          drb=((tan(Teta))*dz)+(C/rb[zl-1]+D_Teta)*dz**2
          Teta=atan(drb/dz)
          vez=ve*cos(Teta)
          ver=ve*sin(Teta)
          ve=sqrt(vez**2+ver**2)
          rb.append(rb[zl-1]+drb)
       NofPlots.set(NofPlots.get()+1)
       Line_Style=lstbox.get(lstbox.curselection())
       if (Line_Style=='Straight'): ST='-'
       if (Line_Style=='Dot'): ST=':'
       if (Line_Style=='Dash'): ST='--'
       if (Line_Style=='Dash-Dot'): ST='-.'
       LW=int(spb2.get())
       ax.plot(Z, rb, color='black', linestyle=ST, linewidth=LW)
       if (Use_Legend.get() == 1):
          if (int(spb3.get()) == 1):
             Legend_Str.set(Legend_Str.get()+str(NofPlots.get())+' - U =  '+entry41.get()+' kV;  ')
          if (int(spb3.get()) == 2):
             Legend_Str.set(Legend_Str.get()+str(NofPlots.get())+' - I =  '+entry42.get()+' A;  ')
          if (int(spb3.get()) == 3):
             Legend_Str.set(Legend_Str.get()+str(NofPlots.get())+' - P =  '+entry43.get()+' Pa;  ')
          if (int(spb3.get()) == 4):
             Legend_Str.set(Legend_Str.get()+str(NofPlots.get())+' - R =  '+entry44.get()+' mm;  ')
          if (int(spb3.get()) == 5):
             Legend_Str.set(Legend_Str.get()+str(NofPlots.get())+' - Alfa =  '+entry45.get()+' deg.;  ')
          if var_rad.get() == 1:
             Gas='Hydrogen'
          if var_rad.get() == 2:
             Gas='Helium'
          if var_rad.get() == 3:
             Gas='Nitrogen'
          if var_rad.get() == 4:
             Gas='Oxigen'
          if (int(spb3.get()) == 6):
             Legend_Str.set(Legend_Str.get()+str(NofPlots.get())+' - '+Gas+'; ')
       ax.grid(color = 'black', alpha = 0.5, linestyle = 'dashed', linewidth = 0.5)
       if (rb[0]>rb[-1])&(rb[0]>rb_out_text):
          rb_out_text=rb[0]
       else:
          if (rb[0]<rb[-1])&(rb[-1]>rb_out_text):
             rb_out_text=rb[-1]
       if ((int(spb3.get()) >= 1)&(int(spb3.get()) <= 4)):
          ax.text(Z[0], rb_out_text, Legend_Str.get())
       if ((int(spb3.get()) == 5)|(int(spb3.get()) == 6)):
          ax.text(Z[0], rb_out_text*1.05, Legend_Str.get())
       if (Use_Legend.get() == 1):
          ax.text(Z[-1]+int(NofPoints/40)*dz, rb[-1], str(NofPlots.get()))
       canvasAgg.draw()
       min_rb=min(rb)
       entry49.delete(0,END)
       Out49_Long=str(min_rb*1000)
       Out49=Out49_Long[0:6]
       entry49.insert(0, Out49)
       for ll in range (1, len(rb)):
          if (rb[ll] == min_rb):
             Z_Focus = Z[ll]
             Point_Focus_Number=ll
       entry410.delete(0,END)
       Out410_Long=str(Z_Focus)
       Out410=Out410_Long[0:6]
       entry410.insert(0, Out410)
       entry411.delete(0,END)
       Out411_Long=str((Ib/(pi*min_rb**2))/1e3)
       Out411=Out411_Long[0:6]
       entry411.insert(0, Out411)
       entry412.delete(0,END)
       Out412_Long=str(((Uac*Ib)/(pi*min_rb**2))/1e6)
       Out412=Out412_Long[0:6]
       entry412.insert(0, Out412)
def makecanvas(txt, bgclr):
    cnvs = Canvas(nb, background = bgclr)
    nb.add(cnvs, text = txt, padding = 3)
    return cnvs
def Manual_Interpolation ():
########################## Checking the Correctness of the Numerical Format of the Input Data#######
    Order_of_Function = spb.get()
    Check_Intp_Data=1;
    entry_err_win.delete(0,END)
    if (int(Order_of_Function) == 2):
       try:
          Z1=float(entry12.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z2=float(entry13.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z3=float(entry14.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R1=float(entry111.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R2=float(entry113.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R3=float(entry114.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R3 coordinate. It is not numerical data. Pleace check input data.')
###### Checking the Correctness of the Numerical Values of the Input Data#######
       if (Z2<Z1):
          entry_err_win.insert(0,'The second z coordinate Z2 should be grater, than the first z coordinate Z1. Pleace check input data.')
          Check_Intp_Data=0
       if (Z3<Z2):
          entry_err_win.insert(0,'The third z coordinate Z3 should be grater, than the second z coordinate Z2. Pleace check input data.')
          Check_Intp_Data=0
##### Basic Calcualtions ###########################################
       if (Check_Intp_Data==1):
          Point1_R=R1; Point2_R=R2; Point3_R=R3
          k1=(Point2_R**2-Point1_R**2)/(Z2-Z1)
          k2=(Point3_R**2-Point1_R**2)/(Z3-Z1)
          k3=(Z2+Z1)/(Z3-Z2)
          a_int2=(k2-k1)/(Z3-Z2)
          b_int2=k1-(k2-k1)*k3
          c_int2=Point1_R**2-a_int2*Z1**2-(k1-(k2-k1)*k3)*Z1
          Z = linspace(Z1, Z3, 1000)
          rb_int=[Point1_R]
          for ll in range (1, len(Z)):
             Intp_Res=sqrt(a_int2*(Z[ll])**2+b_int2*Z[ll]+c_int2)
             rb_int.append(Intp_Res)
########Cleaning the boxes of Z coordinates Z4, Z5, Z6 and Z7 ########
       entry15.delete(0,END)
       entry16.delete(0,END)
       entry17.delete(0,END)
       entry18.delete(0,END)
########Cleaning the boxes of R coordinates R4, R5, R6 and R7 ########
       entry115.delete(0,END)
       entry116.delete(0,END)
       entry117.delete(0,END)
       entry11818.delete(0,END)
###### Output of values of C1, C2 and C3 coefficients into corresponded baxes ###########################################
       entry121.delete(0,END)
       c_out=str(c_int2)
       entry121.insert(0,c_out)
       entry122.delete(0,END)
       b_out=str(b_int2)
       entry122.insert(0,b_out)
       entry123.delete(0,END)
       a_out=str(a_int2)
       entry123.insert(0,a_out)
########Cleaning the boxes of high-order coefficients C4, C5, C6 and C7 ########
       entry124.delete(0,END)
       entry125.delete(0,END)
       entry126.delete(0,END)
       entry12727.delete(0,END)
##############Third Order Root-Polynomial Function##############################
    if (int(Order_of_Function) == 3):
       try:
          Z1=float(entry12.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z2=float(entry13.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z3=float(entry14.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z4=float(entry15.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z4 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R1=float(entry111.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R2=float(entry113.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R3=float(entry114.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R4=float(entry115.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R4 coordinate. It is not numerical data. Pleace check input data.')
###### Checking the Correctness of the Numerical Values of the Input Data#######
       if (Z2<Z1):
          entry_err_win.insert(0,'The second z coordinate Z2 should be grater, than the first z coordinate Z1. Pleace check input data.')
          Check_Intp_Data=0
       if (Z3<Z2):
          entry_err_win.insert(0,'The third z coordinate Z3 should be grater, than the second z coordinate Z2. Pleace check input data.')
          Check_Intp_Data=0
       if (Z4<Z3):
          entry_err_win.insert(0,'The fourth z coordinate Z4 should be grater, than the third z coordinate Z3. Pleace check input data.')
          Check_Intp_Data=0
###### Basic Calcualtions ###########################################
       Point1_R=R1; Point2_R=R2; Point3_R=R3; Point4_R=R4;
       if (Check_Intp_Data==1):
          rb_int=[]
          Z = linspace(Z1, Z4, 1000)
          RP3(Z1, Z2, Z3, Z4, Point1_R, Point2_R, Point3_R, Point4_R)
          for ll in range (0, len(Z)):
             Intp_Res=(C3_3*(Z[ll])**3+C2_3*Z[ll]**2+C1_3*Z[ll]+C0_3)**(1/3)
             rb_int.append(Intp_Res)
########Cleaning the boxes of Z coordinates Z4, Z5, Z6 and Z7 ########
       entry16.delete(0,END)
       entry17.delete(0,END)
       entry18.delete(0,END)
########Cleaning the boxes of R coordinates R4, R5, R6 and R7 ########
       entry116.delete(0,END)
       entry117.delete(0,END)
       entry11818.delete(0,END)
###### Output of values of C1, C2, C3 and C3 coefficients into corresponded baxes ###########################################
       entry121.delete(0,END)
       C0_3_out=str(C0_3)
       entry121.insert(0,C0_3_out)
       entry122.delete(0,END)
       C1_3_out=str(C1_3)
       entry122.insert(0,C1_3_out)
       entry123.delete(0,END)
       C2_3_out=str(C2_3)
       entry123.insert(0,C2_3_out)
       entry124.delete(0,END)
       C3_3_out=str(C3_3)
       entry124.insert(0,C3_3_out)
########Cleaning the boxes of high-order coefficients C5, C6 and C7 ########
       entry125.delete(0,END)
       entry126.delete(0,END)
       entry12727.delete(0,END)
##############Fourth Order Root-Polynomial Function##############################
    if (int(Order_of_Function) == 4):
       try:
          Z1=float(entry12.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z2=float(entry13.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z3=float(entry14.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z4=float(entry15.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z4 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z5=float(entry16.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z5 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R1=float(entry111.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R2=float(entry113.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R3=float(entry114.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R4=float(entry115.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R4 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R5=float(entry116.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R5 coordinate. It is not numerical data. Pleace check input data.')
###### Checking the Correctness of the Numerical Values of the Input Data#######
       if (Z2<Z1):
          entry_err_win.insert(0,'The second z coordinate Z2 should be grater, than the first z coordinate Z1. Pleace check input data.')
          Check_Intp_Data=0
       if (Z3<Z2):
          entry_err_win.insert(0,'The third z coordinate Z3 should be grater, than the second z coordinate Z2. Pleace check input data.')
          Check_Intp_Data=0
       if (Z4<Z3):
          entry_err_win.insert(0,'The fourth z coordinate Z4 should be grater, than the third z coordinate Z3. Pleace check input data.')
          Check_Intp_Data=0
       if (Z5<Z4):
          entry_err_win.insert(0,'The fifth z coordinate Z5 should be grater, than the fourth z coordinate Z4. Pleace check input data.')
          Check_Intp_Data=0
###### Basic Calcualtions ###########################################
       Point1_R=R1; Point2_R=R2; Point3_R=R3; Point4_R=R4; Point5_R=R5;
       if (Check_Intp_Data==1):
          rb_int=[]
          Z = linspace(Z1, Z5, 1000)
          RP4(Z1, Z2, Z3, Z4, Z5, Point1_R, Point2_R, Point3_R, Point4_R, Point5_R)
          for ll in range (0, len(Z)):
             Intp_Res=(C4_4*(Z[ll])**4+C3_4*(Z[ll])**3+C2_4*Z[ll]**2+C1_4*Z[ll]+C0_4)**(1/4)
             rb_int.append(Intp_Res)
########Cleaning the boxes of Z coordinates Z6 and Z7 ########
       entry17.delete(0,END)
       entry18.delete(0,END)
########Cleaning the boxes of R coordinates R6 and R7 ########
       entry117.delete(0,END)
       entry11818.delete(0,END)
###### Output of values of C0, C1, C2, C3 and  coefficients into corresponded baxes ###########################################
       entry121.delete(0,END)
       C0_4_out=str(C0_4)
       entry121.insert(0,C0_4_out)
       entry122.delete(0,END)
       C1_4_out=str(C1_4)
       entry122.insert(0,C1_4_out)
       entry123.delete(0,END)
       C2_4_out=str(C2_4)
       entry123.insert(0,C2_4_out)
       entry124.delete(0,END)
       C3_4_out=str(C3_4)
       entry124.insert(0,C3_4_out)
       entry125.delete(0,END)
       C4_4_out=str(C4_4)
       entry125.insert(0,C4_4_out)
########Cleaning the boxes of high-order coefficients C5 and C6  ########
       entry126.delete(0,END)
       entry12727.delete(0,END)
##############Fifth Order Root-Polynomial Function##############################
    if (int(Order_of_Function) == 5):
       try:
          Z1=float(entry12.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z2=float(entry13.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z3=float(entry14.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z4=float(entry15.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z4 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z5=float(entry16.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z5 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z6=float(entry17.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z6 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R1=float(entry111.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R2=float(entry113.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R3=float(entry114.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R4=float(entry115.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R4 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R5=float(entry116.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R5 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R6=float(entry117.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R6 coordinate. It is not numerical data. Pleace check input data.')
###### Checking the Correctness of the Numerical Values of the Input Data#######
       if (Z2<Z1):
          entry_err_win.insert(0,'The second z coordinate Z2 should be grater, than the first z coordinate Z1. Pleace check input data.')
          Check_Intp_Data=0
       if (Z3<Z2):
          entry_err_win.insert(0,'The third z coordinate Z3 should be grater, than the second z coordinate Z2. Pleace check input data.')
          Check_Intp_Data=0
       if (Z4<Z3):
          entry_err_win.insert(0,'The fourth z coordinate Z4 should be grater, than the third z coordinate Z3. Pleace check input data.')
          Check_Intp_Data=0
       if (Z5<Z4):
          entry_err_win.insert(0,'The fifth z coordinate Z5 should be grater, than the fourth z coordinate Z4. Pleace check input data.')
          Check_Intp_Data=0
       if (Z6<Z5):
          entry_err_win.insert(0,'The sixth z coordinate Z6 should be grater, than the fifth z coordinate Z5. Pleace check input data.')
          Check_Intp_Data=0
###### Basic Calcualtions ###########################################
       Point1_R=R1; Point2_R=R2; Point3_R=R3; Point4_R=R4; Point5_R=R5; Point6_R=R6;
       if (Check_Intp_Data==1):
          rb_int=[]
          Z = linspace(Z1, Z6, 1000)
          RP5(Z1, Z2, Z3, Z4, Z5, Z6, Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R)
          for ll in range (0, len(Z)):
             Intp_Res=(C5_5*(Z[ll])**5+C4_5*(Z[ll])**4+C3_5*(Z[ll])**3+C2_5*Z[ll]**2+C1_5*Z[ll]+C0_5)**(1/5)
             rb_int.append(Intp_Res)
########Cleaning the box of Z coordinates Z7 ########
       entry18.delete(0,END)
########Cleaning the box of R coordinate  R7 ########
       entry11818.delete(0,END)
###### Output of values of C0, C1, C2, C3, C4 and C5 coefficients into corresponded baxes ###########################################
       entry121.delete(0,END)
       C0_5_out=str(C0_5)
       entry121.insert(0,C0_5_out)
       entry122.delete(0,END)
       C1_5_out=str(C1_5)
       entry122.insert(0,C1_5_out)
       entry123.delete(0,END)
       C2_5_out=str(C2_5)
       entry123.insert(0,C2_5_out)
       entry124.delete(0,END)
       C3_5_out=str(C3_5)
       entry124.insert(0,C3_5_out)
       entry125.delete(0,END)
       C4_5_out=str(C4_5)
       entry125.insert(0,C4_5_out)
       entry126.delete(0,END)
       C5_5_out=str(C5_5)
       entry126.insert(0,C5_5_out)
########Cleaning the box of high-order coefficient C6  ########
       entry12727.delete(0,END)
    ##############Sixth Order Root-Polynomial Function##############################
    if (int(Order_of_Function) == 6):
       try:
          Z1=float(entry12.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z2=float(entry13.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z3=float(entry14.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z4=float(entry15.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z4 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z5=float(entry16.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z5 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z6=float(entry17.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z6 coordinate. It is not numerical data. Pleace check input data.')
       try:
          Z7=float(entry18.get())
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of Z7 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R1=float(entry111.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R1 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R2=float(entry113.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R2 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R3=float(entry114.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R3 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R4=float(entry115.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R4 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R5=float(entry116.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R5 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R6=float(entry117.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R6 coordinate. It is not numerical data. Pleace check input data.')
       try:
          R7=float(entry11818.get())/1000
       except:
          Check_Intp_Data=0
          entry_err_win.insert(0,'Wronge value of R7 coordinate. It is not numerical data. Pleace check input data.')
###### Checking the Correctness of the Numerical Values of the Input Data#######
       if (Z2<Z1):
          entry_err_win.insert(0,'The second z coordinate Z2 should be grater, than the first z coordinate Z1. Pleace check input data.')
          Check_Intp_Data=0
       if (Z3<Z2):
          entry_err_win.insert(0,'The third z coordinate Z3 should be grater, than the second z coordinate Z2. Pleace check input data.')
          Check_Intp_Data=0
       if (Z4<Z3):
          entry_err_win.insert(0,'The fourth z coordinate Z4 should be grater, than the third z coordinate Z3. Pleace check input data.')
          Check_Intp_Data=0
       if (Z5<Z4):
          entry_err_win.insert(0,'The fifth z coordinate Z5 should be grater, than the fourth z coordinate Z4. Pleace check input data.')
          Check_Intp_Data=0
       if (Z6<Z5):
          entry_err_win.insert(0,'The sixth z coordinate Z6 should be grater, than the fifth z coordinate Z5. Pleace check input data.')
          Check_Intp_Data=0
       if (Z7<Z6):
          entry_err_win.insert(0,'The seventh z coordinate Z7 should be grater, than the sixth z coordinate Z6. Pleace check input data.')
          Check_Intp_Data=0
###### Basic Calcualtions ###########################################
       Point1_R=R1; Point2_R=R2; Point3_R=R3; Point4_R=R4; Point5_R=R5; Point6_R=R6; Point7_R=R7;
       if (Check_Intp_Data==1):
          rb_int=[]
          Z = linspace(Z1, Z7, 1000)
          RP6(Z1, Z2, Z3, Z4, Z5, Z6, Z7, Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R, Point7_R)
          for ll in range (0, len(Z)):
             Intp_Res=(C6_6*(Z[ll])**6+C5_6*(Z[ll])**5+C4_6*(Z[ll])**4+C3_6*(Z[ll])**3+C2_6*Z[ll]**2+C1_6*Z[ll]+C0_6)**(1/6)
             rb_int.append(Intp_Res)
###### Output of values of C0, C1, C2, C3, C4, C5 and C6 coefficients into corresponded baxes ###########################################
       entry121.delete(0,END)
       C0_6_out=str(C0_6)
       entry121.insert(0,C0_6_out)
       entry122.delete(0,END)
       C1_6_out=str(C1_6)
       entry122.insert(0,C1_6_out)
       entry123.delete(0,END)
       C2_6_out=str(C2_6)
       entry123.insert(0,C2_6_out)
       entry124.delete(0,END)
       C3_6_out=str(C3_6)
       entry124.insert(0,C3_6_out)
       entry125.delete(0,END)
       C4_6_out=str(C4_6)
       entry125.insert(0,C4_6_out)
       entry126.delete(0,END)
       C5_6_out=str(C5_6)
       entry126.insert(0,C5_6_out)
       entry12727.delete(0,END)
       C6_6_out=str(C6_6)
       entry12727.insert(0,C6_6_out)
######## Building graph########
    ax2.clear()
    ax3.clear()
    ax2.plot(Z, rb_int, color = 'black', linewidth = 3)
    if (int(Order_of_Function) == 2):
       ax2.plot([Z1,Z2,Z3], [Point1_R, Point2_R, Point3_R], 'ko', markersize = 8)
    if (int(Order_of_Function) == 3):
       ax2.plot([Z1,Z2,Z3, Z4], [Point1_R, Point2_R, Point3_R, Point4_R], 'ko', markersize = 8)
    if (int(Order_of_Function) == 4):
       ax2.plot([Z1,Z2,Z3,Z4,Z5], [Point1_R, Point2_R, Point3_R, Point4_R, Point5_R], 'ko', markersize = 8)
    if (int(Order_of_Function) == 5):
       ax2.plot([Z1,Z2,Z3,Z4,Z5,Z6], [Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R], 'ko', markersize = 8)
    if (int(Order_of_Function) == 6):
       ax2.plot([Z1,Z2,Z3,Z4,Z5,Z6,Z7], [Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R, Point7_R], 'ko', markersize = 8)
    ax2.grid(color = 'black', alpha = 0.5, linestyle = 'dashed', linewidth = 0.5)
    canvasAgg2.draw()
   ###################################################################
def Import_Data_from_SDE_to_Intrpolation_Task():
   Order_of_Function = spb.get()
   entry_err_win.delete(0,END)
################################# Second Order Root-polynomial Function #######
   if (int(Order_of_Function) == 2):
         Point1_R = rb[10]
         Point2_R = min_rb
         Point3_R = rb[-10]
         entry12.delete(0,END)
         Zout1_Long=str(Z[10]);
         Zout1=Zout1_Long[0:8]
         entry12.insert(0,Zout1)
         entry13.delete(0,END)
         Zout2_Long=str(Z[Point_Focus_Number]);
         Zout2=Zout2_Long[0:8]
         entry13.insert(0,Zout2)
         entry14.delete(0,END)
         Zout3_Long=str(Z[-10]);
         Zout3=Zout3_Long[0:8]
         entry14.insert(0,Zout3)
         entry111.delete(0,END)
         entry16.delete(0,END)
         entry17.delete(0,END)
         entry18.delete(0,END)
         Rout1_Long=str(Point1_R*1000);
         Rout1=Rout1_Long[0:8]
         entry111.insert(0,Rout1)
         entry113.delete(0,END)
         Rout2_Long=str(Point2_R*1000);
         Rout2=Rout2_Long[0:8]
         entry113.insert(0,Rout2)
         entry114.delete(0,END)
         Rout3_Long=str(Point3_R*1000);
         Rout3=Rout3_Long[0:8]
         entry114.insert(0,Rout3)
         entry116.delete(0,END)
         entry117.delete(0,END)
         entry11818.delete(0,END)
         k1=(Point2_R**2-Point1_R**2)/(Z[Point_Focus_Number]-Z[10])
         k2=(Point3_R**2-Point1_R**2)/(Z[-10]-Z[10]);
         k3=(Z[Point_Focus_Number]+Z[10])/(Z[-10]-Z[Point_Focus_Number])
         a_int2=(k2-k1)/(Z[-10]-Z[Point_Focus_Number])
         b_int2=k1-(k2-k1)*k3
         c_int2=Point1_R**2-a_int2*Z[10]**2-(k1-(k2-k1)*k3)*Z[10]
         rb_int=[rb0/1000]
         Err_Res=[0]
         for ll in range (1, len(Z)):
            Intp_Res=sqrt(a_int2*(Z[ll])**2+b_int2*Z[ll]+c_int2)
            rb_int.append(Intp_Res)
            Err_Res.append((abs(rb[ll]-Intp_Res)/rb[ll])*100)
         entry121.delete(0,END)
         c_out=str(c_int2)
         entry121.insert(0,c_out)
         entry122.delete(0,END)
         b_out=str(b_int2)
         entry122.insert(0,b_out)
         entry123.delete(0,END)
         a_out=str(a_int2)
         entry123.insert(0,a_out)
         entry124.delete(0,END)
         entry125.delete(0,END)
         entry126.delete(0,END)
         Zf_Int2=-b_int2/(2*a_int2);
         Rf_Int2=sqrt(c_int2-(b_int2**2)/(4*a_int2));
         entry128.delete(0,END)
         RFout_Long=str(Rf_Int2*1000)
         RFout=RFout_Long[0:8]
         entry128.insert(0,RFout)
         entry129.delete(0,END)
         ZFout_Long=str(Zf_Int2)
         ZFout=ZFout_Long[0:8]
         entry129.insert(0,ZFout)
         entry15.delete(0,END)
         entry115.delete(0,END)
         entry12727.delete(0,END)
         Err_Focus=(abs(Z_Focus-Zf_Int2)/Z_Focus)*100
         Err_Radius=(abs(min_rb-Rf_Int2)/min_rb)*100
         Err_Focus_Out_Long=str(Err_Focus)
         Poz_Z=0
         for il in range(1, len(Err_Focus_Out_Long)):
            if (Err_Focus_Out_Long[il] == 'e'): Poz_Z=il;
         if (Poz_Z!=0):
            Err_Focus_Out_Long_New=Err_Focus_Out_Long[0:4]+Err_Focus_Out_Long[Poz_Z:len(Err_Focus_Out_Long)]
            Err_Focus_Out_Long=Err_Focus_Out_Long_New
         Err_Focus_Out=Err_Focus_Out_Long[0:8]
         Err_Radius_Out_Long=str(Err_Radius)
         Poz_Rad=0
         for il in range(1, len(Err_Radius_Out_Long)):
            if (Err_Radius_Out_Long[il] == 'e'): Poz_Rad=il
         if (Poz_Rad!=0):
            Err_Radius_Out_Long_New=Err_Radius_Out_Long[0:4]+Err_Radius_Out_Long[Poz_Rad:len(Err_Radius_Out_Long)]
            Err_Radius_Out_Long=Err_Radius_Out_Long_New
         Err_Radius_Out=Err_Radius_Out_Long[0:8]
         entry131.delete(0,END)
         entry131.insert(0,Err_Radius_Out)
         entry132.delete(0,END)
         entry132.insert(0,Err_Focus_Out)
################################## Third Order Root-Polynomial Function ############
   if (int(Order_of_Function) == 3):
##################################  Defining of Basic Points to Interpolation ##############
      Point1_R = rb[10]
      Point2_R = rb[Point_Focus_Number-int(NofPoints/20)]
      Point3_R = rb[Point_Focus_Number+int(NofPoints/20)]
      Point4_R = rb[-10]
      Z1=Z[10]
      Z2=Z[Point_Focus_Number-int(NofPoints/20)]
      Z3=Z[Point_Focus_Number+int(NofPoints/20)]
      Z4=Z[-10]
############################ Filling boxes along the Z coordinate ##############
      entry12.delete(0,END)
      Zout1_Long=str(Z[10])
      Zout1=Zout1_Long[0:8]
      entry12.insert(0,Zout1)
      entry13.delete(0,END)
      Zout2_Long=str(Z2)
      Zout2=Zout2_Long[0:8]
      entry13.insert(0,Zout2)
      entry14.delete(0,END)
      Zout3_Long=str(Z3)
      Zout3=Zout3_Long[0:8]
      entry14.insert(0,Zout3)
      entry15.delete(0,END)
      Zout4_Long=str(Z4)
      Zout4=Zout4_Long[0:8]
      entry15.insert(0,Zout4)
      entry16.delete(0,END)
      entry17.delete(0,END)
      entry18.delete(0,END)
###################### Filling boxes along the R coordinate ##############
      entry111.delete(0,END)
      Rout1_Long=str(Point1_R*1000)
      Rout1=Rout1_Long[0:8]
      entry111.insert(0,Rout1)
      entry113.delete(0,END)
      Rout2_Long=str(Point2_R*1000)
      Rout2=Rout2_Long[0:8]
      entry113.insert(0,Rout2)
      entry114.delete(0,END)
      Rout3_Long=str(Point3_R*1000)
      Rout3=Rout3_Long[0:8]
      entry114.insert(0,Rout3)
      entry115.delete(0,END)
      Rout4_Long=str(Point4_R*1000)
      Rout4=Rout4_Long[0:8]
      entry115.insert(0,Rout4)
      entry116.delete(0,END)
      entry117.delete(0,END)
      entry11818.delete(0,END)
      entry12727.delete(0,END)
############################ Basic Calcualtions ######################
      rb_int=[rb0/1000]
      Err_Res=[0]
      RP3(Z1, Z2, Z3, Z4, Point1_R, Point2_R, Point3_R, Point4_R)
      for ll in range (1, len(Z)):
         Intp_Res=(C3_3*(Z[ll])**3+C2_3*Z[ll]**2+C1_3*Z[ll]+C0_3)**(1/3)
         rb_int.append(Intp_Res)
         Err_Res.append((abs(rb[ll]-Intp_Res)/rb[ll])*100)
############################ Displaying Polynomial Coefficients  ######################
      entry121.delete(0,END)
      C0_3_out=str(C0_3)
      entry121.insert(0,C0_3_out)
      entry122.delete(0,END)
      C1_3_out=str(C1_3)
      entry122.insert(0,C1_3)
      entry123.delete(0,END)
      C2_3_out=str(C2_3)
      entry123.insert(0,C2_3_out)
      entry124.delete(0,END)
      C3_3_out=str(C3_3)
      entry124.insert(0,C3_3_out)
      entry125.delete(0,END)
      entry126.delete(0,END)
      Rf_Int3=min(rb_int)
############################ Displaying Focal Beam Parameters  ###############
      for lll in range (1, len(rb_int)):
          if (rb_int[lll] == Rf_Int3): Zf_Int3 = Z[lll]
      entry128.delete(0,END)
      RFout_Long=str(Rf_Int3*1000)
      RFout=RFout_Long[0:8]
      entry128.insert(0,RFout)
      entry129.delete(0,END)
      ZFout_Long=str(Zf_Int3)
      ZFout=ZFout_Long[0:8]
      entry129.insert(0,ZFout)
      Err_Focus=(abs(Z_Focus-Zf_Int3)/Z_Focus)*100
      Err_Radius=(abs(min_rb-Rf_Int3)/min_rb)*100
      Err_Focus_Out_Long=str(Err_Focus)
      Poz_Z=0
      for il in range(1, len(Err_Focus_Out_Long)):
         if (Err_Focus_Out_Long[il] == 'e'): Poz_Z=il;
      if (Poz_Z!=0):
         Err_Focus_Out_Long_New=Err_Focus_Out_Long[0:4]+Err_Focus_Out_Long[Poz_Z:len(Err_Focus_Out_Long)]
         Err_Focus_Out_Long=Err_Focus_Out_Long_New
      Err_Focus_Out=Err_Focus_Out_Long[0:8]
      Err_Radius_Out_Long=str(Err_Radius)
      Poz_Rad=0
      for il in range(1, len(Err_Radius_Out_Long)):
          if (Err_Radius_Out_Long[il] == 'e'): Poz_Rad=il
      if (Poz_Rad!=0):
         Err_Radius_Out_Long_New=Err_Radius_Out_Long[0:4]+Err_Radius_Out_Long[Poz_Rad:len(Err_Radius_Out_Long)]
         Err_Radius_Out_Long=Err_Radius_Out_Long_New
      Err_Radius_Out=Err_Radius_Out_Long[0:8]
      entry131.delete(0,END)
      entry131.insert(0,Err_Radius_Out)
      entry132.delete(0,END)
      entry132.insert(0,Err_Focus_Out)
################################## Fourth Order Root-Polynomial Function ########
   if (int(Order_of_Function) == 4):
##################################  Defining of Basic Points to Interpolation ##############
      Point1_R = rb[10]
      Point2_R = rb[Point_Focus_Number-int(NofPoints/5)]
      Point3_R = rb[Point_Focus_Number]
      Point4_R = rb[Point_Focus_Number+int(NofPoints/5)]
      Point5_R = rb[-10]
      Z1=Z[10]
      Z2=Z[Point_Focus_Number-int(NofPoints/5)]
      Z3=Z[Point_Focus_Number]
      Z4=Z[Point_Focus_Number+int(NofPoints/5)]
      Z5=Z[-10]
############################ Filling boxes along the Z coordinate ##############
      entry12.delete(0,END)
      Zout1_Long=str(Z[10])
      Zout1=Zout1_Long[0:8]
      entry12.insert(0,Zout1)
      entry13.delete(0,END)
      Zout2_Long=str(Z2)
      Zout2=Zout2_Long[0:8]
      entry13.insert(0,Zout2)
      entry14.delete(0,END)
      Zout3_Long=str(Z3)
      Zout3=Zout3_Long[0:8]
      entry14.insert(0,Zout3)
      entry15.delete(0,END)
      Zout4_Long=str(Z4)
      Zout4=Zout4_Long[0:8]
      entry15.insert(0,Zout4)
      entry16.delete(0,END)
      Zout5_Long=str(Z5)
      Zout5=Zout5_Long[0:8]
      entry16.insert(0,Zout5)
      entry17.delete(0,END)
      entry18.delete(0,END)
###################### Filling boxes along the R coordinate ##############
      entry111.delete(0,END)
      Rout1_Long=str(Point1_R*1000)
      Rout1=Rout1_Long[0:8]
      entry111.insert(0,Rout1)
      entry113.delete(0,END)
      Rout2_Long=str(Point2_R*1000)
      Rout2=Rout2_Long[0:8]
      entry113.insert(0,Rout2)
      entry114.delete(0,END)
      Rout3_Long=str(Point3_R*1000)
      Rout3=Rout3_Long[0:8]
      entry114.insert(0,Rout3)
      entry115.delete(0,END)
      Rout4_Long=str(Point4_R*1000)
      Rout4=Rout4_Long[0:8]
      entry115.insert(0,Rout4)
      entry116.delete(0,END)
      Rout5_Long=str(Point5_R*1000)
      Rout5=Rout5_Long[0:8]
      entry116.insert(0,Rout5)
      entry117.delete(0,END)
      entry11818.delete(0,END)
############################ Basic Calcualtions ######################
      rb_int=[rb0/1000]
      Err_Res=[0]
      RP4(Z1, Z2, Z3, Z4, Z5, Point1_R, Point2_R, Point3_R, Point4_R, Point5_R)
      for ll in range (1, len(Z)):
         Intp_Res=(C4_4*(Z[ll])**4+C3_4*(Z[ll])**3+C2_4*Z[ll]**2+C1_4*Z[ll]+C0_4)**(1/4)
         rb_int.append(Intp_Res)
         Err_Res.append((abs(rb[ll]-Intp_Res)/rb[ll])*100)
############################ Displaying Polynomial Coefficients  ######################
      entry121.delete(0,END)
      C0_4_out=str(C0_4)
      entry121.insert(0,C0_4_out)
      entry122.delete(0,END)
      C1_4_out=str(C1_4)
      entry122.insert(0,C1_4)
      entry123.delete(0,END)
      C2_4_out=str(C2_4)
      entry123.insert(0,C2_4_out)
      entry124.delete(0,END)
      C3_4_out=str(C3_4)
      entry124.insert(0,C3_4_out)
      entry125.delete(0,END)
      C4_4_out=str(C4_4)
      entry125.insert(0,C4_4_out)
      entry126.delete(0,END)
      entry12727.delete(0,END)
      Rf_Int4=min(rb_int)
      for lll in range (1, len(rb_int)):
          if (rb_int[lll] == Rf_Int4): Zf_Int4 = Z[lll]
      entry128.delete(0,END)
      RFout_Long=str(Rf_Int4*1000)
      RFout=RFout_Long[0:8]
      entry128.insert(0,RFout)
      entry129.delete(0,END)
      ZFout_Long=str(Zf_Int4)
      ZFout=ZFout_Long[0:8]
      entry129.insert(0,ZFout)
      Err_Focus=(abs(Z_Focus-Zf_Int4)/Z_Focus)*100
      Err_Radius=(abs(min_rb-Rf_Int4)/min_rb)*100
      Err_Focus_Out_Long=str(Err_Focus)
      Poz_Z=0
      for il in range(1, len(Err_Focus_Out_Long)):
         if (Err_Focus_Out_Long[il] == 'e'): Poz_Z=il;
      if (Poz_Z!=0):
         Err_Focus_Out_Long_New=Err_Focus_Out_Long[0:4]+Err_Focus_Out_Long[Poz_Z:len(Err_Focus_Out_Long)]
         Err_Focus_Out_Long=Err_Focus_Out_Long_New
      Err_Focus_Out=Err_Focus_Out_Long[0:8]
      Err_Radius_Out_Long=str(Err_Radius)
      Poz_Rad=0
      for il in range(1, len(Err_Radius_Out_Long)):
          if (Err_Radius_Out_Long[il] == 'e'): Poz_Rad=il
      if (Poz_Rad!=0):
         Err_Radius_Out_Long_New=Err_Radius_Out_Long[0:4]+Err_Radius_Out_Long[Poz_Rad:len(Err_Radius_Out_Long)]
         Err_Radius_Out_Long=Err_Radius_Out_Long_New
      Err_Radius_Out=Err_Radius_Out_Long[0:8]
      entry131.delete(0,END)
      entry131.insert(0,Err_Radius_Out)
      entry132.delete(0,END)
      entry132.insert(0,Err_Focus_Out)
################################## Fifth Order Root-Polynomial Function ########
   if (int(Order_of_Function) == 5):
##################################  Defining of Basic Points to Interpolation ##############
      Point1_R = rb[10]
      Point2_R = rb[Point_Focus_Number-int(NofPoints/3)]
      Point3_R = rb[Point_Focus_Number-int(NofPoints/20)]
      Point4_R = rb[Point_Focus_Number+int(NofPoints/20)]
      Point5_R = rb[Point_Focus_Number+int(NofPoints/3)]
      Point6_R = rb[-10]
      Z1=Z[10]
      Z2=Z[Point_Focus_Number-int(NofPoints/3)]
      Z3=Z[Point_Focus_Number-int(NofPoints/20)]
      Z4=Z[Point_Focus_Number+int(NofPoints/20)]
      Z5=Z[Point_Focus_Number+int(NofPoints/3)]
      Z6=Z[-10]
############################ Filling boxes along the Z coordinate ##############
      entry12.delete(0,END)
      Zout1_Long=str(Z[10])
      Zout1=Zout1_Long[0:8]
      entry12.insert(0,Zout1)
      entry13.delete(0,END)
      Zout2_Long=str(Z2)
      Zout2=Zout2_Long[0:8]
      entry13.insert(0,Zout2)
      entry14.delete(0,END)
      Zout3_Long=str(Z3)
      Zout3=Zout3_Long[0:8]
      entry14.insert(0,Zout3)
      entry15.delete(0,END)
      Zout4_Long=str(Z4)
      Zout4=Zout4_Long[0:8]
      entry15.insert(0,Zout4)
      entry16.delete(0,END)
      Zout5_Long=str(Z5)
      Zout5=Zout5_Long[0:8]
      entry16.insert(0,Zout5)
      entry17.delete(0,END)
      Zout6_Long=str(Z6)
      Zout6=Zout6_Long[0:8]
      entry17.insert(0,Zout5)
      entry18.delete(0,END)
###################### Filling boxes along the R coordinate ##############
      entry111.delete(0,END)
      Rout1_Long=str(Point1_R*1000)
      Rout1=Rout1_Long[0:8]
      entry111.insert(0,Rout1)
      entry113.delete(0,END)
      Rout2_Long=str(Point2_R*1000)
      Rout2=Rout2_Long[0:8]
      entry113.insert(0,Rout2)
      entry114.delete(0,END)
      Rout3_Long=str(Point3_R*1000)
      Rout3=Rout3_Long[0:8]
      entry114.insert(0,Rout3)
      entry115.delete(0,END)
      Rout4_Long=str(Point4_R*1000)
      Rout4=Rout4_Long[0:8]
      entry115.insert(0,Rout4)
      entry116.delete(0,END)
      Rout5_Long=str(Point5_R*1000)
      Rout5=Rout5_Long[0:8]
      entry116.insert(0,Rout5)
      entry117.delete(0,END)
      Rout6_Long=str(Point6_R*1000)
      Rout6=Rout6_Long[0:8]
      entry117.insert(0,Rout6)
      entry11818.delete(0,END)
############################ Basic Calcualtions ######################
      rb_int=[rb0/1000]
      Err_Res=[0]
      RP5(Z1, Z2, Z3, Z4, Z5, Z6, Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R)
      for ll in range (1, len(Z)):
         Intp_Res=(C5_5*(Z[ll])**5+C4_5*(Z[ll])**4+C3_5*(Z[ll])**3+C2_5*Z[ll]**2+C1_5*Z[ll]+C0_5)**(1/5)
         rb_int.append(Intp_Res)
         Err_Res.append((abs(rb[ll]-Intp_Res)/rb[ll])*100)
############################ Displaying Polynomial Coefficients  ######################
      entry121.delete(0,END)
      C0_5_out=str(C0_5)
      entry121.insert(0,C0_5_out)
      entry122.delete(0,END)
      C1_5_out=str(C1_5)
      entry122.insert(0,C1_5)
      entry123.delete(0,END)
      C2_5_out=str(C2_5)
      entry123.insert(0,C2_5_out)
      entry124.delete(0,END)
      C3_5_out=str(C3_5)
      entry124.insert(0,C3_5_out)
      entry125.delete(0,END)
      C4_5_out=str(C4_5)
      entry125.insert(0,C4_5_out)
      entry126.delete(0,END)
      C5_5_out=str(C5_5)
      entry126.insert(0,C5_5_out)
      entry12727.delete(0,END)
      Rf_Int4=min(rb_int)
      for lll in range (1, len(rb_int)):
          if (rb_int[lll] == Rf_Int4): Zf_Int4 = Z[lll]
      entry128.delete(0,END)
      RFout_Long=str(Rf_Int4*1000)
      RFout=RFout_Long[0:8]
      entry128.insert(0,RFout)
      entry129.delete(0,END)
      ZFout_Long=str(Zf_Int4)
      ZFout=ZFout_Long[0:8]
      entry129.insert(0,ZFout)
      Err_Focus=(abs(Z_Focus-Zf_Int4)/Z_Focus)*100
      Err_Radius=(abs(min_rb-Rf_Int4)/min_rb)*100
      Err_Focus_Out_Long=str(Err_Focus)
      Poz_Z=0
      for il in range(1, len(Err_Focus_Out_Long)):
         if (Err_Focus_Out_Long[il] == 'e'): Poz_Z=il;
      if (Poz_Z!=0):
         Err_Focus_Out_Long_New=Err_Focus_Out_Long[0:4]+Err_Focus_Out_Long[Poz_Z:len(Err_Focus_Out_Long)]
         Err_Focus_Out_Long=Err_Focus_Out_Long_New
      Err_Focus_Out=Err_Focus_Out_Long[0:8]
      Err_Radius_Out_Long=str(Err_Radius)
      Poz_Rad=0
      for il in range(1, len(Err_Radius_Out_Long)):
          if (Err_Radius_Out_Long[il] == 'e'): Poz_Rad=il
      if (Poz_Rad!=0):
         Err_Radius_Out_Long_New=Err_Radius_Out_Long[0:4]+Err_Radius_Out_Long[Poz_Rad:len(Err_Radius_Out_Long)]
         Err_Radius_Out_Long=Err_Radius_Out_Long_New
      Err_Radius_Out=Err_Radius_Out_Long[0:8]
      entry131.delete(0,END)
      entry131.insert(0,Err_Radius_Out)
      entry132.delete(0,END)
      entry132.insert(0,Err_Focus_Out)
   ################################## Sixth Order Root-Polynomial Function ########
   if (int(Order_of_Function) == 6):
##################################  Defining of Basic Points to Interpolation ##############
      Point1_R = rb[10]
      Point2_R = rb[Point_Focus_Number-int(NofPoints/3)]
      Point3_R = rb[Point_Focus_Number-int(NofPoints/6)]
      Point4_R = rb[Point_Focus_Number]
      Point5_R = rb[Point_Focus_Number+int(NofPoints/6)]
      Point6_R = rb[Point_Focus_Number+int(NofPoints/3)]
      Point7_R = rb[-10]
      Z1=Z[10]
      Z2=Z[Point_Focus_Number-int(NofPoints/3)]
      Z3=Z[Point_Focus_Number-int(NofPoints/6)]
      Z4=Z[Point_Focus_Number]
      Z5=Z[Point_Focus_Number+int(NofPoints/6)]
      Z6=Z[Point_Focus_Number+int(NofPoints/3)]
      Z7=Z[-10]
############################ Filling boxes along the Z coordinate ##############
      entry12.delete(0,END)
      Zout1_Long=str(Z[10])
      Zout1=Zout1_Long[0:8]
      entry12.insert(0,Zout1)
      entry13.delete(0,END)
      Zout2_Long=str(Z2)
      Zout2=Zout2_Long[0:8]
      entry13.insert(0,Zout2)
      entry14.delete(0,END)
      Zout3_Long=str(Z3)
      Zout3=Zout3_Long[0:8]
      entry14.insert(0,Zout3)
      entry15.delete(0,END)
      Zout4_Long=str(Z4)
      Zout4=Zout4_Long[0:8]
      entry15.insert(0,Zout4)
      entry16.delete(0,END)
      Zout5_Long=str(Z5)
      Zout5=Zout5_Long[0:8]
      entry16.insert(0,Zout5)
      entry17.delete(0,END)
      Zout6_Long=str(Z6)
      Zout6=Zout6_Long[0:8]
      entry17.insert(0,Zout6)
      entry18.delete(0,END)
      Zout7_Long=str(Z7)
      Zout7=Zout7_Long[0:8]
      entry18.insert(0,Zout7)
###################### Filling boxes along the R coordinate ##############
      entry111.delete(0,END)
      Rout1_Long=str(Point1_R*1000)
      Rout1=Rout1_Long[0:8]
      entry111.insert(0,Rout1)
      entry113.delete(0,END)
      Rout2_Long=str(Point2_R*1000)
      Rout2=Rout2_Long[0:8]
      entry113.insert(0,Rout2)
      entry114.delete(0,END)
      Rout3_Long=str(Point3_R*1000)
      Rout3=Rout3_Long[0:8]
      entry114.insert(0,Rout3)
      entry115.delete(0,END)
      Rout4_Long=str(Point4_R*1000)
      Rout4=Rout4_Long[0:8]
      entry115.insert(0,Rout4)
      entry116.delete(0,END)
      Rout5_Long=str(Point5_R*1000)
      Rout5=Rout5_Long[0:8]
      entry116.insert(0,Rout5)
      entry117.delete(0,END)
      Rout6_Long=str(Point6_R*1000)
      Rout6=Rout6_Long[0:8]
      entry117.insert(0,Rout6)
      entry11818.delete(0,END)
      Rout7_Long=str(Point7_R*1000)
      Rout7=Rout7_Long[0:8]
      entry11818.insert(0,Rout7)
############################ Basic Calcualtions ######################
      rb_int=[rb0/1000]
      Err_Res=[0]
      RP6(Z1, Z2, Z3, Z4, Z5, Z6, Z7, Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R, Point7_R)
      for ll in range (1, len(Z)):
         Intp_Res=(C6_6*(Z[ll])**6+C5_6*(Z[ll])**5+C4_6*(Z[ll])**4+C3_6*(Z[ll])**3+C2_6*Z[ll]**2+C1_6*Z[ll]+C0_6)**(1/6)
         rb_int.append(Intp_Res)
         Err_Res.append((abs(rb[ll]-Intp_Res)/rb[ll])*100)
############################ Displaying Polynomial Coefficients  ######################
      entry121.delete(0,END)
      C0_6_out=str(C0_6)
      entry121.insert(0,C0_6_out)
      entry122.delete(0,END)
      C1_6_out=str(C1_6)
      entry122.insert(0,C1_6_out)
      entry123.delete(0,END)
      C2_6_out=str(C2_6)
      entry123.insert(0,C2_6_out)
      entry124.delete(0,END)
      C3_6_out=str(C3_6)
      entry124.insert(0,C3_6_out)
      entry125.delete(0,END)
      C4_6_out=str(C4_6)
      entry125.insert(0,C4_6_out)
      C5_6_out=str(C5_6)
      entry126.delete(0,END)
      entry126.insert(0,C5_6_out)
      entry12727.delete(0,END)
      C6_6_out=str(C6_6)
      entry12727.insert(0,C6_6_out)
      Rf_Int6=min(rb_int)
      for lll in range (1, len(rb_int)):
          if (rb_int[lll] == Rf_Int6): Zf_Int6 = Z[lll]
      entry128.delete(0,END)
      RFout_Long=str(Rf_Int6*1000)
      RFout=RFout_Long[0:8]
      entry128.insert(0,RFout)
      entry129.delete(0,END)
      ZFout_Long=str(Zf_Int6)
      ZFout=ZFout_Long[0:8]
      entry129.insert(0,ZFout)
      Err_Focus=(abs(Z_Focus-Zf_Int6)/Z_Focus)*100
      Err_Radius=(abs(min_rb-Rf_Int6)/min_rb)*100
      Err_Focus_Out_Long=str(Err_Focus)
      Poz_Z=0
      for il in range(1, len(Err_Focus_Out_Long)):
         if (Err_Focus_Out_Long[il] == 'e'): Poz_Z=il;
      if (Poz_Z!=0):
         Err_Focus_Out_Long_New=Err_Focus_Out_Long[0:4]+Err_Focus_Out_Long[Poz_Z:len(Err_Focus_Out_Long)]
         Err_Focus_Out_Long=Err_Focus_Out_Long_New
      Err_Focus_Out=Err_Focus_Out_Long[0:8]
      Err_Radius_Out_Long=str(Err_Radius)
      Poz_Rad=0
      for il in range(1, len(Err_Radius_Out_Long)):
          if (Err_Radius_Out_Long[il] == 'e'): Poz_Rad=il
      if (Poz_Rad!=0):
         Err_Radius_Out_Long_New=Err_Radius_Out_Long[0:4]+Err_Radius_Out_Long[Poz_Rad:len(Err_Radius_Out_Long)]
         Err_Radius_Out_Long=Err_Radius_Out_Long_New
      Err_Radius_Out=Err_Radius_Out_Long[0:8]
      entry131.delete(0,END)
      entry131.insert(0,Err_Radius_Out)
      entry132.delete(0,END)
      entry132.insert(0,Err_Focus_Out)
######################################################################
############################ Building Graph ######################
   ax2.clear()
   ax2.set_xlabel('z, m', fontname='Arial', fontsize=14)
   ax2.set_ylabel('r, m', fontname='Arial', fontsize=14)
   ax2.plot(Z, rb, color = 'black', linewidth = 2)
   if (int(Order_of_Function) == 2):
      ax2.plot([Z[10],Z[Point_Focus_Number],Z[-10]], [Point1_R, Point2_R, Point3_R], 'ko', markersize = 8)
   if (int(Order_of_Function) == 3):
      ax2.plot([Z1,Z2,Z3, Z4], [Point1_R, Point2_R, Point3_R, Point4_R], 'ko', markersize = 8)
   if (int(Order_of_Function) == 4):
      ax2.plot([Z1,Z2,Z3,Z4,Z5], [Point1_R, Point2_R, Point3_R, Point4_R, Point5_R], 'ko', markersize = 8)
   if (int(Order_of_Function) == 5):
      ax2.plot([Z1,Z2,Z3,Z4,Z5,Z6], [Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R], 'ko', markersize = 8)
   if (int(Order_of_Function) == 6):
      ax2.plot([Z1,Z2,Z3,Z4,Z5,Z6, Z7], [Point1_R, Point2_R, Point3_R, Point4_R, Point5_R, Point6_R, Point7_R], 'ko', markersize = 8)
   ax2.plot(Z, rb_int, 'k--', linewidth = 3)
   ax2.grid(color = 'black', alpha = 0.5, linestyle = 'dashed', linewidth = 0.5)
   ax3.clear()
   ax3.set_xlabel('z, m', fontname='Arial', fontsize=14)
   ax3.set_ylabel('Err, %', fontname='Arial', fontsize=14)
   ax3.plot(Z, Err_Res, color = 'black', linewidth = 2)
   ax3.grid(color = 'black', alpha = 0.5, linestyle = 'dashed', linewidth = 0.5)
   canvasAgg2.draw()
window = Tk()
window.title('Electron Beam Boundary Trajectories Interpolation and Approximation')
######################  Creating Canvas  ######################
nb = Notebook(width = 480, height = 360)
nb.pack(expand = 1, fill = 'both')
cnvs1 = makecanvas('Interpolation', '#ffffff')
cnvs2 = makecanvas('Approximation', '#f7ffff')
cnvs3 = makecanvas('Read Image', '#f7ffff')
cnvs4 = makecanvas('Solving of Differential Equation of Beam Boundary Trajectory', '#ffffff')
######################  Interface of Canva 1,  Interpolation  ######################
####################### Defining the Order of Function ##########################
data1 = StringVar()
data1.set('Task Parameters:')
label1=Label(cnvs1, font='Arial 16', background = 'white', textvariable = data1)
label1.place(x = 450, y = 5, width = 250, height = 34)
label1.pack
data1_Order = StringVar()
data1_Order.set('Order of the Root-Polynomial Function:')
label1_Order=Label(cnvs1, font='Arial 14', background = 'white',  textvariable = data1_Order)
label1_Order.place(x = 750, y = 5, width = 350, height = 34)
label1_Order.pack
spb = Spinbox(cnvs1, from_ = 2, to = 6, width = 16, font = 'Arial 10');
spb.place(x = 1070, y = 50, width = 30, height = 30)
spb.set(2)
str1 = 'Import from SDE Task'
btn = Button(cnvs1, text = str1, width = 25, command = Import_Data_from_SDE_to_Intrpolation_Task)
btn.place(x = 1070, y = 100)
str2 = 'Calculate Manually'
btn2= Button(cnvs1, text = str2, command = Manual_Interpolation)
btn2.place(x = 1120, y = 50)
######################  Boxex for Z Coordinates  ######################
data11 = StringVar()
data11.set('z Coordinate, m:')
label11=Label(cnvs1, font='Arial 12', background = 'white', textvariable = data11)
label11.place(x = 20, y = 50, width = 120, height = 34)
label11.pack
data12 = StringVar()
data12.set('1.')
label12=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data12)
label12.place(x = 170, y = 50, width = 20, height = 34)
label12.pack
entry12 = Entry(cnvs1,font='Arial 12')
entry12.place(x = 200, y = 50, width = 75, height = 34)
data13 = StringVar()
data13.set('2.')
label13=Label(cnvs1, font='Arial 14', background = 'white',  textvariable = data13)
label13.place(x = 300, y = 50, width = 20, height = 34)
label13.pack
entry13 = Entry(cnvs1,font='Arial 12')
entry13.place(x = 330, y = 50, width = 75, height = 34)
data14 = StringVar()
data14.set('3.')
label14=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data14)
label14.place(x = 430, y = 50, width = 20, height = 34)
label14.pack
entry14 = Entry(cnvs1,font='Arial 12')
entry14.place(x = 460, y = 50, width = 75, height = 34)
data15 = StringVar()
data15.set('4.')
label15=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data15)
label15.place(x = 560, y = 50, width = 20, height = 34)
label15.pack
entry15 = Entry(cnvs1,font='Arial 12')
entry15.place(x = 590, y = 50, width = 75, height = 34)
data16 = StringVar()
data16.set('5.')
label16=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data16)
label16.place(x = 690, y = 50, width = 20, height = 34)
label16.pack
entry16 = Entry(cnvs1,font='Arial 12')
entry16.place(x = 720, y = 50, width = 75, height = 34)
data17 = StringVar()
data17.set('6.')
label17=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data17)
label17.place(x = 820, y = 50, width = 20, height = 34)
label17.pack
entry17 = Entry(cnvs1,font='Arial 12')
entry17.place(x = 850, y = 50, width = 75, height = 34)
data18 = StringVar()
data18.set('7.')
label18=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data18)
label18.place(x = 950, y = 50, width = 20, height = 34)
label18.pack
entry18 = Entry(cnvs1,font='Arial 12')
entry18.place(x = 980, y = 50, width = 75, height = 34)
######################  Boxex for Beam Radius  ######################
data111 = StringVar()
data111.set('Beam Radius r, mm:')
label111=Label(cnvs1, font='Arial 12', background = 'white', textvariable = data111)
label111.place(x = 20, y = 100, width = 150, height = 34)
label111.pack
data112 = StringVar()
data112.set('1.')
label112=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data112)
label112.place(x = 170, y = 100, width = 20, height = 34)
label112.pack
entry111 = Entry(cnvs1,font='Arial 12')
entry111.place(x = 200, y = 100, width = 75, height = 34)
data113 = StringVar()
data113.set('2.')
label113=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data113)
label113.place(x = 300, y = 100, width = 20, height = 34)
label113.pack
entry113 = Entry(cnvs1,font='Arial 12')
entry113.place(x = 330, y = 100, width = 75, height = 34)
data114 = StringVar()
data114.set('3.')
label114=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data114)
label114.place(x = 430, y = 100, width = 20, height = 34)
label114.pack
entry114 = Entry(cnvs1,font='Arial 12')
entry114.place(x = 460, y = 100, width = 75, height = 34)
data115 = StringVar()
data115.set('4.')
label115=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data115)
label115.place(x = 560, y = 100, width = 20, height = 34)
label115.pack
entry115 = Entry(cnvs1,font='Arial 12')
entry115.place(x = 590, y = 100, width = 75, height = 34)
data116 = StringVar()
data116.set('5.')
label116=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data116)
label116.place(x = 690, y = 100, width = 20, height = 34)
label116.pack
entry116 = Entry(cnvs1,font='Arial 12')
entry116.place(x = 720, y = 100, width = 75, height = 34)
data117 = StringVar()
data117.set('6.')
label117=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data117)
label117.place(x = 820, y = 100, width = 20, height = 34)
label117.pack
entry117 = Entry(cnvs1,font='Arial 12')
entry117.place(x = 850, y = 100, width = 75, height = 34)
data11818 = StringVar()
data11818.set('7.')
label11818=Label(cnvs1, font='Arial 14', background = 'white', textvariable = data11818)
label11818.place(x = 950, y = 100, width = 20, height = 34)
label11818.pack
entry11818 = Entry(cnvs1,font='Arial 12')
entry11818.place(x = 980, y = 100, width = 75, height = 34)
################################################################
fig2 = plt.figure()
ax2 = fig2.add_subplot(2, 1, 1)
ax2.set_xlabel('z, m', fontname='Arial', fontsize=14)
ax2.set_ylabel('r, m', fontname='Arial', fontsize=14)
canvasAgg2 = FigureCanvasTkAgg(fig2, master = cnvs1)
canvasAgg2.draw()
canvas2 = canvasAgg2.get_tk_widget()
canvas2.place(x = 240, y = 150, width = 1000)
ax3 = fig2.add_subplot(2, 1, 2)
ax3.set_xlabel('z, m', fontname='Arial', fontsize=14)
ax3.set_ylabel('Err, %', fontname='Arial', fontsize=14)
data118 = StringVar()
data118.set('1.Interpolation Result:                                   2.Error of Interpolation:')
label118=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue',  textvariable = data118)
label118.place(x = 450, y = 150, width = 900, height = 34)
label118.pack
##################################Displaying Polynomial Coefficients############
data119 = StringVar()
data119.set('Coefficients of Root-Polynomial')
label119=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data119)
label119.place(x = 20, y = 140, width = 300, height = 34)
label119.pack
data120 = StringVar()
data120.set('Function:')
label120=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data120)
label120.place(x = 20, y = 170, width = 100, height = 34)
label120.pack
data121 = StringVar()
data121.set('C0:')
label121=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data121)
label121.place(x = 20, y = 210, width = 50, height = 34)
label121.pack
entry121 = Entry(cnvs1, font='Arial 12')
entry121.place(x = 60, y = 210, width = 210, height = 34)
data122 = StringVar()
data122.set('C1:')
label122=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data122)
label122.place(x = 20, y = 250, width = 50, height = 34)
label122.pack
entry122 = Entry(cnvs1, font='Arial 12')
entry122.place(x = 60, y = 250, width = 210, height = 34)
data123 = StringVar()
data123.set('C2:')
label123=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data123)
label123.place(x = 20, y = 290, width = 50, height = 34)
label123.pack
entry123 = Entry(cnvs1, font='Arial 12')
entry123.place(x = 60, y = 290, width = 210, height = 34)
data124 = StringVar()
data124.set('C3:')
label124=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data124)
label124.place(x = 20, y = 330, width = 50, height = 34)
label124.pack
entry124 = Entry(cnvs1, font='Arial 12')
entry124.place(x = 60, y = 330, width = 210, height = 34)
data125 = StringVar()
data125.set('C4:')
label125=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data125)
label125.place(x = 20, y = 370, width = 50, height = 34)
label125.pack
entry125 = Entry(cnvs1, font='Arial 12')
entry125.place(x = 60, y = 370, width = 210, height = 34)
data126 = StringVar()
data126.set('C5:')
label126=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data126)
label126.place(x = 20, y = 410, width = 50, height = 34)
label126.pack
entry126 = Entry(cnvs1, font='Arial 12')
entry126.place(x = 60, y = 410, width = 210, height = 34)
data12727 = StringVar()
data12727.set('C6:')
label12727=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data12727)
label12727.place(x = 20, y = 450, width = 50, height = 34)
label12727.pack
entry12727 = Entry(cnvs1, font='Arial 12')
entry12727.place(x = 60, y = 450, width = 210, height = 34)
######################################## Displaying Beam Focal Parameters ############
data127 = StringVar()
data127.set('Beam Focal Parameters:')
label127=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data127)
label127.place(x = 1150, y = 150, width = 250,  height = 34)
data128 = StringVar()
data128.set('Beam Radius, mm:')
label128=Label(cnvs1, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data128)
label128.place(x = 1150, y = 190, width = 250,  height = 34)
entry128 = Entry(cnvs1, font='Arial 12')
entry128.place(x = 1300, y = 190, width = 80, height = 24)
data129 = StringVar()
data129.set('Focus Position, m:')
label129=Label(cnvs1, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data129)
label129.place(x = 1150, y = 230, width = 250,  height = 34)
entry129 = Entry(cnvs1, font='Arial 12')
entry129.place(x = 1300, y = 230, width = 80, height = 24)
data130 = StringVar()
data130.set('Error of Interpolation, %:')
label130=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data130)
label130.place(x = 1150, y = 270, width = 250,  height = 34)
data131 = StringVar()
data131.set('Along Beam Radius:')
label131=Label(cnvs1, font='Arial 11', background = 'white', foreground = 'blue', textvariable = data131)
label131.place(x = 1150, y = 310, width = 250,  height = 34)
entry131 = Entry(cnvs1, font='Arial 12')
entry131.place(x = 1300, y = 310, width = 80, height = 24)
data132 = StringVar()
data132.set('Along Focus Position:')
label132=Label(cnvs1, font='Arial 11', background = 'white', foreground = 'blue', textvariable = data132)
label132.place(x = 1150, y = 350, width = 250,  height = 34)
entry132 = Entry(cnvs1, font='Arial 12')
entry132.place(x = 1300, y = 350, width = 80, height = 24)
data133 = StringVar()
data133.set('Error Window:')
label_err_win=Label(cnvs1, font='Arial 14', background = 'white', foreground = 'red', textvariable = data133)
label_err_win.place(x = 20, y = 650, width = 140, height = 34)
entry_err_win = Entry(cnvs1, font='Arial 12')
entry_err_win.place(x = 170, y = 650, width = 980, height = 34)
######################  Interface of Canva 2,  Approximation  ##################
data2 = StringVar()
data2.set('Task Parameters:')
label2=Label(cnvs2, font='Arial 16', background = 'white',  textvariable = data2)
label2.place(x = 450, y = 5, width = 250, height = 34)
label2.pack
data21 = StringVar()
data21.set('Beam Radius r:')
label21=Label(cnvs2, font='Arial 14', background = 'white', textvariable = data21)
label21.place(x = 20, y = 100, width = 150, height = 34)
label21.pack
entry21 = Entry(cnvs2,font='Arial 14')
entry21.place(x = 170, y = 50, width = 900,height = 34)
data22 = StringVar()
data22.set('z Coordinate:')
label22=Label(cnvs2, font='Arial 14', background = 'white', textvariable = data22)
label22.place(x = 20, y = 50, width = 120, height = 34)
label22.pack
entry22 = Entry(cnvs2,font='Arial 14')
entry22.place(x = 170, y = 100, width = 900,height = 34)
#Interface of Canva 4, Solving of Differential Equation of Beam Boundary Trajectory  ######################
data4 = StringVar()
data4.set('Task Parameters:')
label4=Label(cnvs4, font='Arial 20', background = 'white', textvariable = data4)
label4.place(x = 450, y = 5, width = 250, height = 34)
label4.pack
data41 = StringVar()
data41.set('1. Accelaration Voltage, kV:')
label41=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data41)
label41.place(x = 20, y = 50, width = 220, height = 34)
label41.pack
entry41 = Entry(cnvs4, font='Arial 14')
entry41.place(x = 260, y = 50, width = 50, height = 34)
data42 = StringVar()
data42.set('2. Beam Current, A:')
label42=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data42)
label42.place(x = 320, y = 50, width = 150, height = 34)
label42.pack
entry42 = Entry(cnvs4, font='Arial 14')
entry42.place(x = 480, y = 50, width = 50, height = 34)
data43 = StringVar()
data43.set('3. Operation Pressure, Pa:')
label43=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data43)
label43.place(x = 540, y = 50, width = 220, height = 34)
label43.pack
entry43 = Entry(cnvs4, font='Arial 14')
entry43.place(x = 760, y = 50, width = 50, height = 34)
data44 = StringVar()
data44.set('4.Start Beam Radius, mm:')
label44=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data44)
label44.place(x = 20, y = 100, width = 220, height = 34)
label44.pack
entry44 = Entry(cnvs4, font='Arial 14')
entry44.place(x = 260, y = 100, width = 50, height = 34)
data45 = StringVar()
data45.set('5. Start Angle of Beam Convergence, Deg:')
label45=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data45)
label45.place(x = 420, y = 100, width = 420, height = 34)
label45.pack
entry45 = Entry(cnvs4, font='Arial 14')
entry45.place(x = 760, y = 100, width = 50, height = 34)
data46 = StringVar()
data46.set('Start Point z Coordinate, m:')
label46=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data46)
label46.place(x = 20, y = 150, width = 250, height = 34)
label46.pack
entry46 = Entry(cnvs4, font='Arial 14')
entry46.place(x = 260, y = 150, width = 50,height = 34)
data47 = StringVar()
data47.set('Last Point z')
label47=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data47)
label47.place(x = 335, y = 135, width = 250, height = 34)
label47.pack
data471 = StringVar()
data471.set('Coordinate, m:')
label471=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data471)
label471.place(x = 335, y = 160, width = 250, height = 34)
label471.pack
entry47 = Entry(cnvs4, font='Arial 14')
entry47.place(x = 480, y = 150, width = 100,height = 34)
data48 = StringVar()
data48.set('Number of Points')
label48=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data48)
label48.place(x = 600, y = 135, width = 150, height = 34)
label48.pack
data49 = StringVar()
data49.set('on z Coordinate:')
label49=Label(cnvs4, font='Arial 13', background = 'white', textvariable = data49)
label49.place(x = 600, y = 160, width = 150, height = 34)
label49.pack
entry48 = Entry(cnvs4, font='Arial 14')
entry48.place(x = 760, y = 150, width = 50,height = 34)
frmradio4 = LabelFrame(cnvs4, text='6. Choose Operation Gas')
frmradio4.place(x = 250, y = 200, width = 320, height = 40)
frmedit4 = Frame(cnvs4)
frmedit4.pack()
Bi=1
var_rad = IntVar()
rb41 = Radiobutton(frmradio4, text='Hydrogen', variable=var_rad, value=1, command=arb)
rb42 = Radiobutton(frmradio4, text='Helium', variable=var_rad, value=2, command=arb)
rb43 = Radiobutton(frmradio4, text='Nitrogen', variable=var_rad, value=3, command=arb)
rb44 = Radiobutton(frmradio4, text='Oxygen', variable=var_rad, value=4, command=arb)
var_rad.set(1)
rb41.pack(side = 'left')
rb42.pack(side = 'left')
rb43.pack(side = 'left')
rb44.pack(side = 'left')
frameUp = Frame(cnvs4, relief = GROOVE, height = 64)
frameUp.pack(side = BOTTOM, fill = X)
fig = plt.figure()
ax = fig.add_subplot(1, 1, 1)
ax.set_xlabel('z,m', fontname='Arial', fontsize=14)
ax.set_ylabel('r,m', fontname='Arial', fontsize=14)
canvasAgg = FigureCanvasTkAgg(fig, master = frameUp)
canvasAgg.draw()
canvas = canvasAgg.get_tk_widget()
canvas.pack(fill=Y, expand=1)
##################################### Error Window #####################################
data5 = StringVar()
data5.set('Error Window:')
label5=Label(cnvs4, font='Arial 14', background = 'white', foreground = 'red', textvariable = data5)
label5.place(x = 20, y = 250, width = 420, height = 34)
label5.pack
entry5 = Entry(cnvs4, font='Arial 9')
entry5.place(x = 20, y = 280, width = 800, height = 34)
##################################### The Button "Calculate and Building Graph" #####################################
NofPlots=IntVar()
NofPlots.set(0)
rb_out_text=0
btn41 = Button(cnvs4, text = 'Calculate and Building Graph')
btn41.bind('<Button-1>', Check_Errors)
btn41.place(x = 840, y = 280, width = 300, height = 34)
btn42 = Button(cnvs4, text = 'Finish and Create New Graph')
btn42.bind('<Button-1>', Clear_Graph)
btn42.place(x = 900, y = 550, width = 200, height = 34)
##################################### Focal Parameters #####################################
data410 = StringVar()
data410.set('Beam Focal Parameters')
label410=Label(cnvs4, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data410)
label410.place(x = 900, y = 320, width = 250,  height = 34)
data411 = StringVar()
data411.set('Beam Radius, mm:')
label411=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data411)
label411.place(x = 900, y = 355, width = 250,  height = 34)
entry49 = Entry(cnvs4, font='Arial 12')
entry49.config(background = 'gray')
entry49.place(x = 1040, y = 360, width = 70, height = 24)
data412 = StringVar()
data412.set('Focus Position, m:')
label412=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data412)
label412.place(x = 900, y = 395, width = 250,  height = 34)
entry410 = Entry(cnvs4, font='Arial 12')
entry410.config(background = 'gray')
entry410.place(x = 1040, y = 400, width = 70, height = 24)
data413 = StringVar()
data413.set('Current Density,')
label413=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data413)
label413.place(x = 900, y = 430, width = 250,  height = 34)
data414 = StringVar()
data414.set('kA/sq.m:')
label414=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data414)
label414.place(x = 900, y = 455, width = 250,  height = 34)
entry411 = Entry(cnvs4, font='Arial 12')
entry411.config(background = 'gray')
entry411.place(x = 1040, y = 455, width = 70, height = 24)
data415 = StringVar()
data415.set('Power Density,')
label415=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data415)
label415.place(x = 900, y = 480, width = 250,  height = 34)
data416 = StringVar()
data416.set('MW/sq.m:')
label416=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data416)
label416.place(x = 900, y = 505, width = 250,  height = 34)
entry412 = Entry(cnvs4, font='Arial 12')
entry412.config(background = 'gray')
entry412.place(x = 1040, y = 505, width = 70, height = 24)
data417 = StringVar()
data417.set('Define Line Parameters:')
label417=Label(cnvs4, font='Arial 14', background = 'white', foreground = 'blue', textvariable = data417)
label417.place(x = 840, y = 20, width = 250,  height = 34)
data418 = StringVar()
data418.set('Width:')
label418=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data418)
label418.place(x = 840, y = 50, width = 250,  height = 34)
spb2 = Spinbox(cnvs4, from_ = 1, to = 4, width = 16, font = 'Arial 10');
spb2.place(x = 840, y = 85, width = 30, height = 30)
spb2.set(1)
data419 = StringVar()
data419.set('Style:')
label419=Label(cnvs4, font='Arial 12', background = 'white', foreground = 'blue', textvariable = data419)
label419.place(x = 900, y = 47, width = 250,  height = 40)
iflist = LabelFrame(cnvs4, borderwidth = 1, relief = SUNKEN, width = 250, height = 40)
iflist.place(x = 900, y = 78, width = 100, height = 40)
lstbox=Listbox(iflist, borderwidth = 1, height = 40)
lstbox.pack()
lst=StringVar()
lst = ['Straight', 'Dot', 'Dash', 'Dash-Dot']
for elem in lst:
    lstbox.insert(END, elem)
lstbox.selection_set(first = 1)
Legend_Str = StringVar()
Use_Legend = IntVar()
check = Checkbutton(cnvs4, text = 'Use Legend', variable = Use_Legend)
Use_Legend.set(0)
Legend_Str.set('')
check.place(x = 900, y = 120, width = 100, height = 40)
spb3 = Spinbox(cnvs4, from_ = 1, to = 6, width = 16, font = 'Arial 10');
spb3.place(x = 900, y = 150, width = 30, height = 30)
spb3.set(1)
data420 = StringVar()
data420.set('Changeable')
label420=Label(cnvs4, font='Arial 10', background = 'white', foreground = 'blue', textvariable = data420)
label420.place(x = 820, y = 120, width = 80,  height = 40)
data421 = StringVar()
data421.set('Parameter:')
label421=Label(cnvs4, font='Arial 10', background = 'white', foreground = 'blue', textvariable = data421)
label421.place(x = 820, y = 150, width = 80,  height = 40)
window.mainloop()
