import matplotlib.pyplot as plt
import matplotlib.lines as lines
import numpy as np
#Below I import several functions we will need.
#For newbies, the numpy version of sine, cosine etc is NOT THE SAME
#as the "math" version.  The Math version only operates on single numbers,
#but the numpy version operates automatically on arrays of numbers -- much
#more useful for science in general.  If you do not know about this
#difference, numpy will greatly frustrate you.  I have tried to
#take the frustration out of this sample code so that you can just
#think about filling in the math.
from numpy import sqrt,sin,cos,pi

#STUDENTS MAY WANT TO CHANGE SOME OF THESE CONSTANTS
idstr='By R. Sonnenfeld, New Mexico Tech Physics (March 2021) -- Free for educational use only.'
suptitle='Griffith''s Figure 9.16'
title='by. YOUR NAME HERE!!!'
res=900
mu=1.26e-6
mu2=mu;mu1=mu;n1=1.0;n2=1.0
pi=np.pi

def sind(theta):
    """Implements sine in degrees instead of radians"""
    return sin(np.radians(theta))

def cosd(theta):
    """Implements cosine in degrees instead of radians"""
    return cos(np.radians(theta))

#STUDENTS NEED ONLY MODIFY THESE FOUR FUNCTIONS TO DO THE RIGHT THING
def alpha(thetaI,n1,n2):
    a=thetaI #This is a place holder -- replace with a proper calculation
    #print("thetaI=",thetaI)  # This is there for debugging
    return a

def beta(mu1,n1,mu2,n2):
    b=1 #This is a place holder -- replace with a proper calculation
    print("mu1, n1, mu2, n2",(mu1,n1,mu2,n2))
    return b

def Ereflected(alpha,beta):
    Er=alpha  #This is a place holder -- replace with proper calculation
    return Er

def Etransmitted(alpha,beta):
    Et=0.9*alpha  #This is a place holder -- replace with proper calculation
    return Et


#Students should not need to mess with any of the code in "main"
def main():
     print("SPN4-4, 2021: "+ title)
     print("====== ======= =========")
     print(" ")
     print("This template has been stripped down.  Fill in the right math.")
     thetaI=np.linspace(0,89.9,res)
     a=alpha(thetaI,n1,n2)
     b=beta(mu1,n1,mu2,n2)
     Et=Etransmitted(a,b)
     Er=Ereflected(a,b)
     fig,ax=plt.subplots()
     ax.plot(thetaI,Et,thetaI,Er)
     ax.add_artist(lines.Line2D([0,  90], [0, 0],linestyle='--'))
     plt.xlabel('$\\theta_I$',fontsize=18)
     plt.suptitle(suptitle,fontsize=16)
     plt.title(title,fontsize=12)
     plt.legend(('$E_T/E_I$','$E_R/E_I$'),loc='best')
     plt.savefig('SPN4-4s.png')
     plt.show()

main()
