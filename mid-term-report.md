## The paper: **[The effects of seeing on Sersic profiles - II. The Moffat PSF](https://ui.adsabs.harvard.edu/abs/2001MNRAS.328..977T/abstract)**
#
# Summary of this articles
In this paper, the authors discuss the effect of the seeing considering a Moffat PSF. In the end, the authors give a prescription to obtain the seeing-free quantities of the parameters of the Sersic profile from the convolved quantities.
# The Moffat PSF

The **circular** Moffat function is:

$$PSF(r)=\frac{\beta-1}{\pi a^2}[1+(\frac{r}{a})^2]^{-\beta}$$

- The full-width at half-maximum: FWHM$=2\alpha\sqrt{2^{1/\beta}-1}$
- This function has normalize the total flux to 1.
- the value of $\beta$
  - $\beta=5$ to simulate the turbulence prediction
  - $\beta=2.5$ the default value of the *IRAF* package
  - $\beta=1.5$ to model a large 'wings' in the PSF
  - $\beta\sim4.765$ the optimum value to mathc the atmospheric turbulence prediction of the PSF
  - $\beta\rightarrow\infty$ is Gaussian PSF. *For parctical purposes, a value of $\beta=100$ is completely satisfactory for modelling a Gaussian by using a Moffat function.*

# A prescription for seeing correction
In order to obtain a seeing-free Sersic parameters, the auther give a prescription for seeing correction.
- Determine the FWHM and the value of $\beta$. From FWHM and $\beta$, we can know the value of $\alpha$
- Measure $r_e^c$ along the semimajor axis directly from the raw images
- Determine $\eta(r^c_e)$ with the expression $\eta(r^c_e)=\frac{1}{r^c_e}\frac{I_c(r^c_e)}{\frac{dI_c(\xi)}{d\xi}|_{r^c_e}}ln\frac{I_c(r^c_e)}{I_c(0)}$
- Evalutate the vaue of n and $\epsilon$ from Fig.5. 
- Obtain the value of $r_e$ using Fig.4. From the steps above, we get the Moffat PSF parameters $\beta$ and FWHM, 
- Obtain the value of I(0) using Fig.3.

# Q&A
- **What is the advantage of Moffat PSF compared to Gaussian PSF?**
  - Section 2: *It is numerically well behaved in the treatment of narrow PSFs and it allows the 'wings' that usually appear in stellar profiles to be fitted*
    - When we convolute betweem PSF and the model profiles of the galaxies, the inner part of the galaxy profiles are steep which means more computating resources. Narrow PSFs magnify this problems because of the steeper profile. Moffat functions use **polymoials** instead of exponential expression to avoid excessive computational resources. So Moffat PSF is numerically well behaved.
  - Section 2.4: *The presence of these bigger 'wings' in real images makes Moffat functions a bettter choice to model the PSF than the turbulence theory prediction.*
    - The optimal value of $\beta$~4.765 best fit the turbulance of the atmosphere turbulance. But atmosphere turbulance is one of the factors that affect the seeing. The **imperfections in telescope optics** also affect the seeing. So the typical value of $\beta$ should be **smaller**.
- **What is the typical value of $\beta$?**
  - Section 3.2: *For the values of $\beta$ typically present in real images (2.5<$\beta$<4; seee Saglia et al. 1993) we obtain deviations from Gaussian seeing in the range 15-30 per cent (bigger deviatioins are obtained for smllaer values of the ratio $r^c_e$/FWHM)*
  - It's 2.5<$\beta$<4.
- **What is a typical value of the ratio of the effective radius to the FWHM when the Gaussian PSF is in sufficient?**
  - Section5: *It is not sufficient to consider the PSF as Gaussian and assume circular symmetry to model the effects of seeing on the surface brightness distribution when the ratio of the effective radius to the FWHM is small ($\le2.5$)*
  - The ratio of the effective radius to the FWHM is $\le2.5$.
- **What is the 'wings'?**
  - Section 1: *The existence of 'wings' in stellar profiles reveals the real PSF deviates from the Gaussian form.*
  - I think it's related to the second order derivative. For Gaussian PSF, the 'wings' is small because the absolute value of second order derivative is small. So the Gaussian PSF looks steeper. For Moffat PSF with small $\beta$, the 'wings' is large because the absolute value of second order derivative is large. So the Moffat PSF looks more gradual.
- **What is T01?**
  - Section 1 : *Recently, Trujillo et al. (2001, hereafter T01) extended previous work by studying analytically the effects of seeing on elliptically symmetric surface brightness distributions, following the Sersic (1968) $r^{1/4}$ law and assuming a Gaussian point spread function PSF.*
  - It's de Vaucouleur profile with Gaussian PSF.
- **Give a general idea of the impact of seeing**
  - Section 1: *It is well known that the ability to parametrize galaxies from ground-based images is severely compromised by seeing, which scatters light from the objects, thereby producing a loss of resolution in the images, lower mean surface brightnesses than the true values, and larger effective radii.*
  - Lower mean surface brightness, larger effecitve radius
- **What is the effect of the seeing on the central intensity?**
  - Section 2.2: *... the effect on the central intensity of the seeing convolved distribution is a function of the intrinsic ellipticity of the object. Basically, as $\epsilon$ increases, the spread of photons from the inner parts of the profile due to the seeing is more efficient and consequently the central intensity decreases.*
  - Section 3.1: *... the central intensity of profiles with larger values of n is more affected than for low n, as is expected because of the higher central light concentration of these profiles*
  - Higher **intrinsic ellipticity**, more affected by seeing and lower central intensity consequently. Higher **Sersic index n** is also more affected by the seeing.
- **What is the effect of the seeing on the isophotes?**
  - Section 2.3: *In the absence of seeing, by construction, all isophotes of the profile have the same ellipticity, whereas the presence of seeing tends to make them circular.*
  - Seeing makes the isophote circular.
- **What is the effect of the seeing on the effective radius considering different intrinsic ellipticity and Sersic index n? Which one is more important?**
  - Section 3.2: *As n increases, the convolved effective radius also increase. Greater ellipticities result in greater effective radii and these are more importnat for greater values of n.*
  - Larger sersic index n or larger ellipticities result in greater effective radius. The effect of ellipticities is more significant.
- **Why lower value of n is expected without considering the effect of seeing?**
  - Section 3.3: *Note that seeing effects always produce a surface brightness profile with a smaller value of n than the actual one. It is expected that any procedure to recover the structural parameters of the profile that does not take into account the effect of seeing will obtain lower values of n than the actual ones. Lower values of n will be also expected if the intrinsic ellipticities of the objects are not taken into account during the recovery process.*
  - Because of the seeing we observed a darker surface brightness profile and seeing also affect the intrinsic ellipticitese of the objects.
- **What is the effect of the seeing on the mean surface brightness considering different $\beta$ and intrinsic ellipticity?**
  - Section 3.4: *... galaxies affected by seeing have apparent mean surface brightnesses lower than their true values. Lower values of $\beta$ produce greater effects on this quantity. Also, as the intrinsic ellipticity of the object increases, the effect of the seeing on the mean effecitve surface brightness also increase.*
  - Lower $\beta$ greater effects. Larger intrinsic ellipticity greater effects.