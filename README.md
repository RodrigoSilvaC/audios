# audios
Convertir audio a texto utilizando google cloud speech 

### convertir formato de audio 
Esta función se usa para convertir el formato del audio 
#elegir carpeta donde se encuentran los archivos
print("Elige la carpeta donde se encuentran los audios")
filename = filedialog.askdirectory()
os.chdir(filename)


# #convertir audios .mp3 y .wma en .wav
for f in os.listdir(os.getcwd()):
    if f.endswith(".mp3") or f.endswith(".wma"):
        subprocess.call(['ffmpeg', '-i', f,
                   f +'.wav'])
    else:
        continue
        
# # crear nueva carpeta 
os.mkdir("./audios5")
carpeta = os.path.join(os.getcwd(),"audios5")

for files in os.listdir(filename):
    if files.endswith(".wav"):
        shutil.move(files, carpeta)
