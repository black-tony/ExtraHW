# ExtraHW
 JiWang ExtraHW

----------------
#### TODO_�����
1. ��ssl��֤���ļ����ϵ���Ŀ¼��
-----------------------
## ~~ʹ�����ݿ�ķ���~~ ʹ�������ݿ��server���������еķ���

�Ȱ�װmariadb

- ���ݿ���û�Ҫ����`root`(���ڿ��ܻ��)
- ���ݿ������Ҫ����`A6080o--a__TtVFR`

mariadb��ʼ��: ִ��`python ./initdatabase.py`����

`initdatabase.py` Ĭ��ʹ��`./user.sql`, ���Ҫ����ָ��sql�ļ���Ҫʹ�������в���


`python initdatabase.py <�ļ���>`


����init.py��ʱ������������´���
```
ModuleNotFoundError: No module named 'MySQLdb' flask
```
��Ҫִ������ָ��
```shell
pip install mysqlclient
```

-----------------------
## ʹ�������ļ��ķ���
Ĭ�������ļ�Ϊ`./webrtc-Tony.conf`, ֱ��ִ��`python init.py`�Ļ��ͻ�ʹ����������ļ�

�����Ҫʹ�������������ļ�, ����ʹ�������в���

`python init.py <�ļ���>`

�����ļ�������֧�ֵ�������, �����ļ��в����ֵ�����ʹ��Ĭ��ֵ, Ĭ��ֵ�������ļ�ʾ������
```properties
[root_dir]
dir = /home/webrtc/video # ¼�񱣴�λ��, ��ʱ���ò���

[frame]
width=1920
    high =    1080 # �߶�

rate = 15 ;ÿ��֡��

[����ʱ��]
disconnect=15 #����15s����ʾ

[ssl]
crt = /etc/pki/tls/certs/cert.crt # crt�ļ���λ��
key = /etc/pki/tls/private/cert.key # key�ļ���λ��
```
-----------------------

# �ͻ���������ͨ�ŷ���:
ʹ��socketIO

C����S����Ϣ:(C��д��)

�ڿͻ��˵�js�ļ��������������
```javascript
socket = io() //��������

//data��callback������������
//���������function���ڿͻ����յ�Server�����¼���ʱ��ִ��
socket.on('�¼���', function(data, callback){
    ...
    //data�ĸ�ʽ��{name:value}�ĸ�ʽ
    //����ͨ��data['name']����data.name�ĸ�ʽ���ʴ��͵�����
    //callback���Բ�д, �ǻص�����, ������ò���
    //�ͻ����յ���Ϣ�����callback(����), �������������˶�Ӧ�ĺ����Ļ�, ����˻��ж�Ӧ�Ĵ���
    //callback������: �ͻ���ִ��callback("event received!");
    //�������˵ĶԸ�callback�Ķ�����print(arg), �Ƿ���˾ͻ����������ַ���



});

```

S����C����Ϣ:(C��д��)

�ڿͻ��˵�js�ļ��������������
```javascript
socket = io() //ͬ��, һ������ֻ��Ҫһ�����
//��ʽΪsocket.emit('�¼���', data, callback);
//����:
socket.emit('client_event', {num1 : 114514, str1: "1919810"}, function(data){
    console.log("server received data", data);
}
//server���յ���Ϊ'client_event'���¼�
//server���յ�{num1 : 114514, str1: "1919810"}���ݰ�, 
//server���ִ����callback����, ��ͻ��˻��ܵ�����, �ڿ���̨���������
```

# ����ʽ
���û��`python`��`pip`����, ������һ����û��`python3`, `pip3`
```shell
pip install Flask
pip install configparser
pip install Flask-SocketIO
pip install Flask-SQLAlchemy
pip install mysqlclient # ����init.py��ʱ�������ʾû��MySQLdb, ��Ҫ�������
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


