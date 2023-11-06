# SHRIRAAM-T
#include <stdio.h>
double Vgs=-1.5;
double Vp=-2.0;
double Idss=1.8;
double R1=10.0;
double R2=20.0;
double Vcc=15.0;
double Rs=5.0;
int main() {
double Vg = (R2/(R1+R2))*Vcc;
if (Vg<Vp){
    double Id=Idss*(1-(Vg/Vp)*(Vg/Vp));
    printf("Voltage Divider Bias:\n");
    printf("Gate Voltage (Vg): %.2f V\n",Vg);
    printf("Drain Current (Id): %.3f mA\n\n",Id);} 
    else{
        printf("Voltage Divider Bias:\n");
        printf("JFET is in the 'OFF' state\n\n");
    }
    double Vgs_self=-2.0;
    if (Vgs_self<Vp) {
        double Id_self = Idss * (1 - (Vgs_self / Vp) * (Vgs_self / Vp));
        printf("Self-Bias:\n");
        printf("Gate-Source Voltage (Vgs): %.2f V\n",Vgs_self);
        printf("Drain Current (Id): %.3f mA\n\n",Id_self);
    }else{
        printf("Self-Bias:\n");
        printf("JFET is in the 'OFF' state\n\n");}
    double Vg_fixed = -1.0;
    if (Vg_fixed < Vp) {
        double Id_fixed=Idss * (1- (Vg_fixed/Vp)*(Vg_fixed/Vp));
        printf("Fixed Bias:\n");
        printf("Gate Voltage (Vg): %.2f V\n", Vg_fixed);
        printf("Drain Current (Id): %.3f mA\n\n", Id_fixed);} 
        else{
        printf("Fixed Bias:\n");
        printf("JFET is in the 'OFF' state\n\n");}
        return 0;
}
