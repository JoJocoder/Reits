#Download the stock data of Reits from Yahoo finance
#JoJoCoder 2017-12-25
from pandas_datareader import data 
import matplotlib.pyplot as plt  
import matplotlib.finance as mpf  
import pandas as pd
import numpy as np
import matplotlib as mpl
import time
mpl.rcParams['font.family'] = 'sans-serif'
mpl.rcParams['font.sans-serif'] = [u'SimHei']

   
# Set the time  
start_date = '2012-12-4' # Start date
end_date = '2017-12-5'  # End date  

OFFICE=['ARE','BXP','BDN','CIO','CXP','OFC','CUZ','DEI','DEA','ESRT','EQC','FSP','GOV','HIW','HPP','KRC','CLI','NYRT','NRE','PCFO','PGRE','PDM','SLG','TIER','VNO']
INDUSTRIAL=['DCT','DRE','EGP','FR','IIPR','IRM','LPT','MNR','PLYM','PLD','REXR','STAG','TRNO']
RETAIL=['ADC',	'BRX',	'CBL',	'CDR',	'DDR',	'FRT',	'FCPT',	'GTY',	'GGP',	'KIM',	'KRG',	'MAC',	'NNN',	'PEI',	'RPT',	'O',	'REG',	'ROIC',	'RPAI',	'BFS',	'SRG',	'SPG',	'SRC',	'SKT',	'TCO',	'UE',	'UBA',	'VER',	'WPG',	'WRI',	'WHLR',	'WSR']
LODGING=['APLE',	'AHP',	'AHT',	'CLDT',	'CHSP',	'CDOR',	'DRH',	'GLPI',	'HT',	'HPT',	'HST',	'IHT',	'LHO',	'MGP',	'PK',	'PEB',	'RLJ',	'RHP',	'SOHO',	'INN',	'SHO',	'XHR']	
RESIDENTIAL=['RESI',	'ACC',	'AMH',	'AIV',	'AVB',	'BRG',	'BRT',	'CPT',	'EDR',	'ELS',	'EQR',	'ESS',	'IRT',	'INVH',	'MAA',	'NXRT',	'APTS',	'RVEN',	'SFR',	'SUI',	'UDR',	'UMH']
HEALTH=['CTRE',	'CHCT',	'GBCS',	'GMRE',	'HCP',	'HR',	'HTA',	'LTC',	'MRT',	'MPW',	'NHI',	'SNR',	'OHI',	'DOC',	'QCP',	'SBRA',	'SNH',	'UHT',	'VTR',	'HCN']
INFRASTRUCTURE=['AMT','CORR','CCI','HIFR','PW','SBAC','UNIT']
DATA=['COR','CONE','DLR','EQIX','QTS']
DIVERSIFIED=['ALEX',	'ALX',	'AAT',	'AHH',	'CMCT',	'CLPR',	'CLNS',	'EPR',	'FREVS',	'FCE.A',	'GOOD',	'GNL',	'GPT',	'GYRO',	'HMG',	'IRET',	'STAR',	'JBGS',	'LXP',	'OLP',	'PDNLB',	'PSB',	'SAFE',	'SIR',	'STOR',	'WPC',	'WRE']
SPECIALTY=['CTT',	'CXW',	'CUBE',	'EXR',	'FPI',	'GEO',	'LAND',	'SELF',	'LAMR',	'LSI',	'NSA',	'OUT',	'PCH',	'PSA',	'RYN',	'WY']
MORTGAGE=['MITT',	'AGNC',	'ACMC',	'NLY',	'ANH',	'ARI',	'ABR',	'ACRE',	'ARR',	'BXMT',	'CMO',	'CHMI',	'CIM',	'CVHL',	'CYS',	'DX',	'EARN',	'OAKS',	'GPMT',	'AJX',	'HASI',	'IVR',	'JERT',	'JCAP',	'KREF',	'LADR',	'MFA',	'MTGE',	'NRZ',	'NYMT',	'NTHT',	'ORC',	'ORM',	'PMT',	'RAS',	'RWT',	'RSO',	'SACH',	'STWD',	'SLD',	'TRTX',	'TRMT',	'TWO',	'UDFI',	'WMC']
names=[RESIDENTIAL,HEALTH,INFRASTRUCTURE,DATA,DIVERSIFIED,SPECIALTY,MORTGAGE]
titles=['OFFICE','INDUSTRIAL','RETAIL','LODGING','RESIDENTIAL','HEALTH','INFRASTRUCTURE','DATA','DIVERSIFIED','SPECIALTY','MORTGAGE']   
fig, ax = plt.subplots(facecolor=(0.5, 0.5, 0.5))  
fig.subplots_adjust(bottom=0.2)  
ax.xaxis_date()   
plt.xticks(rotation=45)  

plt.xlabel("Time")  
plt.ylabel("Price")  

failedname=[]
count=1
for name in names:
	for num in name:
		done=False
		try_times = 0
		while not done:
			try:
				n=data.get_data_yahoo(str(num),start_date,end_date)
				n.to_excel('\\{}.xlsx'.format(titles[count-1],num))
				print('{} Successs'.format(num))
				done=True
			except Exception as e:
					try_times += 1
					print('{}The{} time try'.format(num,try_times))
					if try_times == 10:
						print('{} failed'.format(num))
						failedname.append(num)
						break
	count+=1
print(failedname)
