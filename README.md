# ExtraHW
 JiWang ExtraHW


#### TODO_�����
1. ��ssl��֤���ļ����ϵ���Ŀ¼��

# ����ʽ
���û��`python`��`pip`����, ������һ����û��`python3`, `pip3`
```shell
pip install Flask
pip install Flask-SocketIO
pip install Flask-SQLAlchemy
pip install pyOpenSSL
python init.py 
```
��װ��python�Ŀ�Ϳ���ֱ������`init.py`��

��Ҫ���Լ�����https��ǩ��, ��httpЭ��webrtc���񲻺�ʹ

ssl���ɵ������ļ�λ�ú��ļ�����Ҫ�̶�~~(��Ϊ·��д����)~~, ������Ҫ��init.py�ļ��и�`ssl_certificate`��`ssl_certificate_key`��ֵ

���ɵ�.crt�ļ�������`/etc/pki/tls/certs/cert.crt`

���ɵ�.key�ļ�������`/etc/pki/tls/private/cert.key`

д��html�ļ���Ҫ����templates�ļ�����, ���������ļ���, ֧���ɷ�����ڴ�һ��html��ʱ���ṩһЩ��Ϣ, ����
```html
ѧ��: <input type="number" name="ID" value="{{user_id}}"> <br>
```
`{{������}}`���ָ�ʽ�ı�������flask��ʾhtml��ʱ������ṩ����Ϣ, �����ʹ�õ�python����Ϊ``render_template("index.html", user_id=user_id)

����һ������ʾ��ʱ��Ὣvalue�� `{{user_id}}`�滻Ϊpython�����`user_id`������ֵ, �����ǿ�, ������ʽΪ

![����](./photo_readme/render.png)


