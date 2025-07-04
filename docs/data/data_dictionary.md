# Diccionario de datos

## Base de datos Clinicas_2019_2025

**Esta BD contiene la informacion de concentracion inhibitoria minica CIM de cada antibiotico, y cada microorganismo aislado de un cultivo de paciente para cualquier secrecion o muestra desde los años 2019 a mayo de 2025

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
|	 COUNTRY_A 	|	Pais paciente	|	categorio	|	Listado paises	|	Whonet	|
|	 LABORATORY 	|	Nombre laboratorio clinico	|	categorio	|	CPR, CF	|	Whonet	|
|	 ORIGIN 	|	Origen de la muestra	|	categorio	|	h, a, vacio	|	Whonet	|
|	 PATIENT_ID 	|	N° documento paciente	|	numerico	|	numeros de id	|	Whonet	|
|	 LAST_NAME 	|	apellidos del paciente	|	texto	|	apellidos	|	Whonet	|
|	 FIRST_NAME 	|	nombres de paciente	|	texto	|	nombres	|	Whonet	|
|	 SEX 	|	sexo paciente	|	texto	|	f, m	|	Whonet	|
|	 DATE_BIRTH 	|	fecha nacimiento paciente	|	fecha	|	fechas de nacimiento	|	Whonet	|
|	 AGE 	|	edad paciente	|	numerico	|	0 a 130	|	Whonet	|
|	 PAT_TYPE 	|	tipo de paciente	|	categorio	|	ped, new, adu	|	Whonet	|
|	 WARD 	|	servicio de toma de muestra	|	categorio	|	uci pe, uci neo, uci adu, etc	|	Whonet	|
|	 INSTITUT 	|	clinica	|	categorio	|	CPR, CF	|	Whonet	|
|	 DEPARTMENT 	|	departamento	|	categorio	|	mix, ped, adu, etc	|	Whonet	|
|	 WARD_TYPE 	|	tipo de servicio	|	categorio	|	icu, eme, urg, inx	|	Whonet	|
|	 DATE_ADMIS 	|	fecha de ingreso	|	fecha	|	vacio	|	Whonet	|
|	 SPEC_NUM 	|	numero de muestra	|	numerico	|	rango de numero de muestras	|	Whonet	|
|	 SPEC_DATE 	|	fecha de muestra	|	fecha	|	rango de fechas	|	Whonet	|
|	 SPEC_TYPE 	|	codigo tipo de muestra	|	categorio	|	rango de tipo de muestras	|	Whonet	|
|	 LOCAL_SPEC 	|	descripcion tipo muestra	|	categorio	|	rango de descripcion tipo muestra	|	Whonet	|
|	 SPEC_CODE 	|	codigo de muesta	|	numerico	|	rango de valores	|	Whonet	|
|	 SPEC_REAS 	|	empty	|	empty	|	empty	|	Whonet	|
|	 ISOL_NUM 	|	empty	|	empty	|	empty	|	Whonet	|
|	 ORGANISM 	|	siglas de microorganismo	|	categorio	|	siglas de microorganismos	|	Whonet	|
|	 LOCAL_ORG 	|	nombre de microorganismo	|	categorio	|	nombres de microorganismos	|	Whonet	|
|	 ORG_TYPE 	|	tipo de microorganismos	|	categorio	|	"+,-, f"	|	Whonet	|
|	 SEROTYPE 	|	empty	|	empty	|	empty	|	Whonet	|
|	 MRSA 	|	empty	|	empty	|	empty	|	Whonet	|
|	 VRE 	|	empty	|	empty	|	empty	|	Whonet	|
|	 BETA_LACT 	|	empty	|	empty	|	empty	|	Whonet	|
|	 ESBL 	|	empty	|	empty	|	empty	|	Whonet	|
|	 MRSA_SCRN 	|	empty	|	empty	|	empty	|	Whonet	|
|	 INDUC_CLI 	|	empty	|	empty	|	empty	|	Whonet	|
|	 COMMENT 	|	empty	|	empty	|	empty	|	Whonet	|
|	 DATE_DATA 	|	fecha de modificacion 	|	fecha	|	rango de fechas	|	Whonet	|
|	 X_EDTA 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_APB 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_IAD 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_ISO 	|	empty	|	empty	|	empty	|	Whonet	|
|	 AMK_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 AMB_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 AMP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 SAM_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 ATM_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CZO_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 FEP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CTX_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 FOX_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CPT_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CAZ_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CZA_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CZT_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CRO_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CIP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CLI_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 DAP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 ETP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 ERY_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 FLU_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 FOS_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 GEN_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 GEH_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 IPM_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 LVX_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 LNZ_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 MEM_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 MIF_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 MFX_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 NIT_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 NOR_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 OXA_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 PEN_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 TZP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 RIF_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 STH_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 TCY_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 TGC_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 SXT_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 VAN_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 VOR_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 NAL_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 AMC_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CTC_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CCV_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 PIP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 TCC_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 TOB_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 MCZ_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 AXS_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 AZM_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CEC_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 TIC_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CPA_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CARBAPENEM 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_CARBA_NP 	|	empty	|	empty	|	empty	|	Whonet	|
|	 ROW_IDX 	|	identificador de columna	|	numerico	|	numero de columnas	|	Whonet	|
|	 X_CARBA5 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_C_MIC 	|	empty	|	empty	|	empty	|	Whonet	|
|	 FCT_NM 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_THM 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_MCIM 	|	empty	|	empty	|	empty	|	Whonet	|
|	 X_GEN_CARB 	|	empty	|	empty	|	empty	|	Whonet	|
|	 CXM_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 DOR_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 QDA_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CEP_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CHL_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 MNO_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 CXA_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 COL_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 TEC_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
|	 MAN_NM 	|	nombre de atb 	|	numerico	|	0,001 a >256	|	Whonet	|
![image](https://github.com/user-attachments/assets/46d3c60a-ab82-4199-8048-af4e1fbadc5e)





- **Variable**: nombre de la variable.
- **Descripción**: breve descripción de la variable.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: fuente de los datos de la variable.

## Base de datos de etiquetas

**Esta Base de datos contiene la informacion de etiquetas en formato Sensible, Intermedio y Resistente (SIR) que corresponde a cada microorganismo y antibiotico.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
|	 PATIENT_ID 	|	N° documento paciente	|	numerico	|	numeros de id	|	BD Whonet	|
|	 SEX 	|	sexo paciente	|	texto	|	f, m	|	Whonet	|
|	 DATE_BIRTH 	|	fecha nacimiento paciente	|	fecha	|	fechas de nacimiento	|	Whonet	|
|	 AGE 	|	edad paciente	|	numerico	|	0 a 130	|	Whonet	|
|	 PAT_TYPE 	|	tipo de paciente	|	categorio	|	ped, new, adu	|	Whonet	|
|	 WARD 	|	servicio de toma de muestra	|	categorio	|	uci pe, uci neo, uci adu, etc	|	Whonet	|
|	 INSTITUT 	|	clinica	|	categorio	|	CPR, CF	|	Whonet	|
|	 SPEC_NUM 	|	numero de muestra	|	numerico	|	rango de numero de muestras	|	Whonet	|
|	 SPEC_DATE 	|	fecha de muestra	|	fecha	|	rango de fechas	|	Whonet	|
|	 SPEC_TYPE 	|	codigo tipo de muestra	|	categorio	|	rango de tipo de muestras	|	Whonet	|
|	 LOCAL_SPEC 	|	descripcion tipo muestra	|	categorio	|	rango de descripcion tipo muestra	|	Whonet	|
|	 SPEC_CODE 	|	codigo de muesta	|	numerico	|	rango de valores	|	Whonet	|
|	 ORGANISM 	|	siglas de microorganismo	|	categorio	|	siglas de microorganismos	|	Whonet	|
|	 LOCAL_ORG 	|	nombre de microorganismo	|	categorio	|	nombres de microorganismos	|	Whonet	|
|	 Eti_AMB_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_AMK_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_AMP_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_ATM_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CAS_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CAZ_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CHL_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CIP_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CLI_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CPT_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CRO_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CTX_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CZA_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CZO_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CZO_NMu 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_CZT_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_DAP_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_ERY_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_ETP_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_FEP_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_FLU_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_FOS_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_FOX_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_GEH_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_GEN_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_GEH_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_IPM_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_LNZ_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_LVX_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_MCZ_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_MEM_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_MFX_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_MIF_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_NIT_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_NOR_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_OXA_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_PEN_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_RIF_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_SAM_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_STH_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_SXT_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_TCY_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_TGC_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_TZP_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_VAN_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_GEH_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
|	 Eti_VOR_NM 	|	nombre de antibioticos	|	categorio	|	S,I,R	|	BD Whonet	|
![image](https://github.com/user-attachments/assets/60d4eb75-14a3-42b7-858e-58863791339e)


- **Variable**: nombre de la variable.
- **Descripción**: breve descripción de la variable.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: fuente de los datos de la variable.
