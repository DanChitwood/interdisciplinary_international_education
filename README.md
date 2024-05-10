# Interdisciplinarity through internationality: results from a US-Mexico graduate course bridging computational and plant science

### Materials and Methods

***Curriculum and classroom environment***

The graduate class for which data was collected originated from a National Science Foundation (NSF) Research Traineeship (NRT) grant at Michigan State University (MSU) called IMPACTS (Integrated training model in Plant And Compu-Tational Sciences; \#1828149; NRT-IMPACTS, 2024). There were five main training objectives to the grant: 1) Proficiency in core knowledge in plant & computational science, 2) Expertise in interdisicplinary research in plant biology & computation, 3) Development of communication, leadership, & management skills, 4) Development of trainees' teaching skills, and 5) Development of trainees' mentoring skills. To address the first point, a series of classes were created to teach and integrate plant biology and computational science learning objectives. The course we describe in this manuscript was the first in the series and titled *HRT841: Foundations in Computational and Plant Sciences*. The course started in 2019 and in 2019 and 2020 consisted only of MSU students. Using Jupyter notebooks (Kluyver et al., 2016), an interactive coding environment with markdown text and in which media are embedded that is used for research, scientific reproducibility, and educational purposes (and with which the analysis for this manuscript are carried out), the class introduces biology students with no prior coding experience and computational students with no prior experimental experience to introdctory coding lessons inspired by biology in Python. The class also teaches command line and bioinformatics. In the second half of the course, students collaborate and author a class project that applies computational approaches to a plant biology question. For example class projects, see published projects from 2019 (Bryson et al., 2020), 2020 (Palande et al., 2023a), and 2021 (Palande et al., 2023b). 

When the COVID-19 pandemic began in 2020 forcing higher educational insitutions worldwide to shutdown, the course focus on computational approaches and the electronic format of Jupyter notebooks with embedded YouTube video lectures that could easily be disseminated provided an opportunity to expand our student audience. The shift to a virtual environment percipitated by the pandemic also permitted us to experiment with international education. In 2021, we expanded the course to include students from the Universidad Nacional Autónoma de México (UNAM) system. The students took the course for credit as *Bioinformática y minería de datos con python*. We published the materials online as a Jupyter book titled *Plants&Python* in English and Spanish for anyone with an internet connection to access the materials (VanBuren et al., 2022; Williams, 2022). Using a flipped classroom approach, students would use the published educational materials and work together in groups during class on a Discord server. After the pandemic, we have continued to use a hybrid approach, with MSU students optionally attending class in person with instructors, Mexican students participating virtually, and the online Discord server serving as a communication channel and digital archive for the yearly class project.

***Survey***

In 2020 (the second year of the course) we began administering a survey to determine the degree that dueling plant biology and computational science learning objectives were being effectively taught. The survey was given before, at the middle, and end of the semester and asked students to self-assess their expertise across biology and computational science topics. In 2020 there were only MSU students that were enrolled in plant biology or computational/data science programs that were easily classified into "biology" and "computational" groups. For the remaining years of the survey (2021 to 2023), we also included students from the UNAM system. Mexican students were located throughout Mexico and enrolled in diverse academic programs (for example, animal science, chemistry, epidemiology, medical and veterinary sciences, evolutionary biology, etc.) and could not be classified into "biology" and "computational" groups. For the years 2021 to 2023, students were assigned to "MSU" and "UNAM" groups. We added a few more questions to the survey beginning in 2021 that asked about new learning objectives as well as working across languages and countries.

Survey questions asked students to self-assess their expertise on a 1 to 10 scale for the following categories: 1) coding, 2) statistics, 3) modeling, 4) bioinformatics, 5) computational resources, 6) molecular biology, 7) genetics & breeding, 8) plant development, 9) phylogenetics, 10) working on a team, 11) project management, 12) interdisciplinary, 13) science communication, and 14) scientific writing. Three additional questions were added for the years 2021 to 2023: 15) command line, 16) working across countries, and 17) working across languages.

This study was determined to be exempt under the Revised Common Rule under 45 CFR 46.104(d) 1, 4ii by the MSU Institutional Review Board (IRB) on 3 April 2024 (MSU Study ID: STUDY00010594).

***Modeling and data analysis***

Using Linear Discriminant Analysis (LDA) we created two different classification models. LDA models a categorical variable as an function of numerous continuous varaibles. For the number of modeled categorical variable groups n, LDA returns n-1 discriminant axes that maximize the differences between groups. In this study we always model two groups, which returns one discriminant axis, which conveniently summarizes modeled group differences based on numerous survey questions as a single value. The weighted contributions of the variables to the classification are known as scalings and provide insights into how the model is working and the most important contributing factors that comprise it. Once an LDA model is created, new data can be projected onto the model and classified. The first model classifies students as belonging to biology or computational groups and is built using only 2020 data from MSU students. We then use this model to classify MSU and UNAM students as belonging to biology or computational groups for the years 2021 to 2023. The second model uses only data from 2021 to 2023 and classifies students as belonging to MSU or UNAM groups.

Data was imported using the pandas module (McKinney, 2010) as a dataframe. Masking was used to isolate specific factor levels as needed. Data scaling, LDA modeling, and cross-validation of models were performed using the scikit-learn (Pedregosa et al., 2011) functions StandardScaler, LinearDiscriminantAnalysis, and RepeatedStratifiedKFold functions, respectively. Significant differences between Linear Discriminant scores were determined using a Kruskal-Wallis test with the stats.kruskal function from the scipy (Virtanen et al., 2020) stats module. All analyses and visualizations were performed in Python using numpy (Harris et al., 2020), matplotlib (Hunter, 2007), and seaborn (Waskom, 2021) modules.

### References

Bryson, A.E., Wilson Brown, M., Mullins, J., Dong, W., Bahmani, K., Bornowski, N., Chiu, C., Engelgau, P., Gettings, B., Gomezcano, F. Gregory, L.M., et al. 2020. Composite modeling of leaf shape along shoots discriminates Vitis species better than individual leaves. Applications in plant sciences, 8(12), p.e11404.

Harris, C.R., Millman, K.J., Van Der Walt, S.J., Gommers, R., Virtanen, P., Cournapeau, D., Wieser, E., Taylor, J., Berg, S., Smith, N.J. and Kern, R., 2020. Array programming with NumPy. Nature, 585(7825), pp.357-362.

Hunter, J.D., 2007. Matplotlib: A 2D graphics environment. Computing in science & engineering, 9(03), pp.90-95.

Kluyver, T., Ragan-Kelley, B., Pérez, F., Granger, B.E., Bussonnier, M., Frederic, J., Kelley, K., Hamrick, J.B., Grout, J., Corlay, S. and Ivanov, P., 2016. Jupyter Notebooks-a publishing format for reproducible computational workflows. Elpub, 2016, pp.87-90.

McKinney, W., 2010, June. Data structures for statistical computing in Python. In SciPy (Vol. 445, No. 1, pp. 51-56).

Palande, S., Kaste, J.A., Roberts, M.D., Segura Abá, K., Claucherty, C., Dacon, J., Doko, R., Jayakody, T.B., Jeffery, H.R., Kelly, N. Manousidaki, A., et al. 2023a. Topological data analysis reveals a core gene expression backbone that defines form and function across flowering plants. PLoS Biology, 21(12), p.e3002397.

Palande, S., Arsenault, J., Basurto-Lozada, P., Bleich, A., Brown, B.N., Buysse, S.F., Connors, N.A., Adhikari, S.D., Dobson, K.C., Guerra-Castillo, F.X. Guerrero-Carrillo, M.F., et al. 2023b. Expression-based machine learning models for predicting plant tissue identity. bioRxiv, pp.2023-08.

Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., Blondel, M., Prettenhofer, P., Weiss, R., Dubourg, V. and Vanderplas, J., 2011. Scikit-learn: Machine learning in Python. the Journal of machine Learning research, 12, pp.2825-2830.

NRT-IMPACTS. 2024. Interfacing Plant and Computational Sciences. Accessed 2 May 2024 https://impacts.natsci.msu.edu/

VanBuren, R., Rougon-Cardoso, A., Amézquita, E.J., Coss-Navarrete, E.L., Espinosa-Jaime, A., Gonzalez-Iturbe, O.A., Luckie-Duque, A.C., Mendoza-Galindo, E., Pardo, J., Rodríguez-Guerrero, G. Rosiles-Loeza, P.Y., et al. 2022. Plants & Python: A series of lessons in coding, plant biology, computation, and bioinformatics. Plant Cell, 34(7).

Virtanen, P., Gommers, R., Oliphant, T.E., Haberland, M., Reddy, T., Cournapeau, D., Burovski, E., Peterson, P., Weckesser, W., Bright, J. and Van Der Walt, S.J., 2020. SciPy 1.0: fundamental algorithms for scientific computing in Python. Nature methods, 17(3), pp.261-272.

Waskom, M.L., 2021. Seaborn: statistical data visualization. Journal of Open Source Software, 6(60), p.3021.

Williams, M. 2022. New Teaching Tool, "Plants and Python: a series of lessons in coding, plant biology, computation, and bioinformatics". The Plant Cell: News. Accessed 2 May 2024 https://plantae.org/new-teaching-tool-plants-and-python/

### Figure Legends

**Figure 1: Biology vs. computational student LDA. A)** An LDA model was constructed for biology vs. computational student identity as a function of MSU student survey responses in 2020. Linear discriminant scores for initial, mid, and final semester survey responses were calculated from the model for biology and computational student groups in 2020 and MSU and UNAM student groups 2021 to 2023. **B)** Scalings for linear discriminant scores. More negative scaling values indicate a survey question that contributes towards negative linear discriminant scores, and likewise more positive scaling values indicate survey questions that contribute to positive linear discrimninant scores.

![alt_text](https://github.com/DanChitwood/interdisciplinary_international_education/blob/main/figures/Figure1.jpg)

**Figure 2: MSU vs. UNAM student LDA. A)** An LDA model was constructed for MSU vs. UNAM student identity as a function of student survey responses from 2021 to 2023. Linear discriminant scores for initial, mid, and final semester survey responses were calculated from the model for MSU and UNAM student groups 2021 to 2023. **B)** Scalings for linear discriminant scores. More negative scaling values indicate a survey question that contributes towards negative linear discriminant scores, and likewsie more positive scaling values indicate survey questions that contribute to positive discriminant scores.

![alt_text](https://github.com/DanChitwood/interdisciplinary_international_education/blob/main/figures/Figure2.jpg)

**Table 1: p values for linear discriminant value comparisons for the biology vs. computational student model.**

**Table 2: p values for linear discriminant value comparisons for the MSU vs. UNAM model.**
