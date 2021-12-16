# YouTube-Downloader by r0tt3n-m3m0ry

Программа для автоматизации загрузки аудио и видео с каналов на youtube с возможностью объединять каналы в категории. Программа способна подгружать видео, которые еще не были скачаны, но на канале есть (появились после последнего запуска), для этого и написана. По факту, эта программа - обертка над youtube-dl, чтобы систематизировать скачанные видео. Лично я закинул файлы этой программы в директорию /videos/youtube своего внешнего жесткого диска, и подгружаю видео просто запуском этой программы. Директории категорий будут созданы в текущей директории, так что запускайте программу из директории, в которую хотите загружать видео.

# UPD - уведомления в Windows 10

В Windows 10 по окончанию загрузки видео из каждого источника и по окончанию работы программы в центр уведомлений выводятся соответствующие уведомления. Использовалась библиотека plyer, также установится из requirements.txt. ПОКА НЕ РАБОТАЕТ В .exe ФАЙЛЕ! ПРОБЛЕМА РЕШАЕТСЯ.

# 16.12.2021 UPD - переход на yt-dlp

Youtube-dl умер, и уже как пару месяцев. Скорость загрузки около 70 кбит в секунду при скорости подключения 250 мбит меня не устраивает, поэтому софтинка начинает использовать новую библиотеку.

# Установка

Windows:

Здесь же, на GitHub, во вкладке Releases, находится исполняемый файл для windows. Поместите его перед запуском в директорию, в которую хотите устанавливать видео, например на флешку или внешний жесткий диск, туда же поместите файл с данными для загрузки.

MD5 хеш исполняемого файла v1.0-win: 4f042d89f23e785eea4ba79b33dc2514 
MD5 хеш исполняемого файла v1.1-win: f9c4d72ec5d66ecace00482707a38dbb

Linux, MacOS:

$ git clone https://github.com/r0tt3n-m3m0ry/youtube-downloader  
$ cd youtube-downloader  
$ pip3 install -r requirements.txt  
$ python3 downloader.py  

Если вы хотите запускать программу по команде в терминале, выполните следующие команды:

$ mv downloader.py ~  
$ alias название_команды='python3 ~/downloader.py'

# youtube-authors-list.txt

ВАЖНО! Удалите содержимое файла перед тем, как заполнить его своими данными! По умолчанию там есть одна тестовая категория из двух каналов!

Этот файл содержит необходимую для загрузки видео и разбиения каналов на категории информацию. Каждый канал или плейлист указывается на отдельной строке в следующем виде: 

https://www.youtube.com/channel/author_name <<>> тип загружаемых данных <<>> название директории-категории <<>> название директории-канала

Ссылка обязательно должна начинаться с протокола (http или https), иначе будет проигнорирована

Тип загружаемых данных - либо video, либо audio. В первом случае качается видео, во втором аудио. ВАЖНО! выполните $ sudo apt install ffmpeg ffprobe для того, чтобы аудио корректно конвертировались в mp3 (иначе сохраняются как mpeg)

# Баги, недоработки

1. Пользователю всё ещё нужно установить ffmpeg и ffprobe самостоятельно :(

# Связаться со мной
Таки остались вопросы или появились предложения? Напишите мне на почту hk.labmem001@gmail.com для связи, отвечу как только смогу
