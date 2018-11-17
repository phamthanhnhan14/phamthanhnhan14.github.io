Thử search google với từ khóa “jira crack” thì ta sẽ thấy rất nhiều kết quả có liên quan, từ tool crack hay tip, từ tiếng Việt tới tiếng Anh, đây thực sự là 1 mối quan tâm của rất nhiều người là tester, system admin, hay là sinh viên…

Mình cũng đã tìm kiếm, cài đặt và active thành công với các software của atlassian như Jira Software, Jira ServiceDesk, plugin … dựa theo tut sau.

Hiện tại thì link trên đã bị report do vi phạm DMCA

> 

https://github.com/calfzhou/atlassian-license-study

Có thể dùng link thay thế [ở đây](https://drive.google.com/drive/folders/1-NYkal4dR49Q0Cm99OxUMkufdsKofTDN) nhé!!!

Nếu bạn là system admin, có 1 chút hiểu biết về lập trình, biết cài java, maven, biết đọc, sửa code python thì thực sự đơn giản với bạn. Chỉ cần thực hiện [step by step](https://github.com/calfzhou/atlassian-license-study/blob/develop/EXAMPLE.md) là OK, bạn không cần theo dõi tiếp bài viết này nữa nhé, vì trên đó là đủ dùng rồi.:)

Tuy nhiên vẫn có rất nhiều người không thực hiện được điều này.

Vậy hãy theo dõi hướng dẫn chi tiết ở[ bài viết trước](https://chuyencuasys.com/2016/10/10/install-jira-on-centos-7/) nhé.

Có 1 số thay đổi đó là:

Download bản cài đặt mới nhất từ trang chủ https://www.atlassian.com/software/jira/download

Bản hiện tại là 7.5 cho Jira Software, Jira Service Desk 3.8.1

Dùng mysql version 5.7 trở lên

Cài đặt Apache Maven:

> # wget [http://mirror.cc.columbia.edu/pub/software/apache/maven/maven-3/3.5.0/binaries/apache-maven-3.5.0-bin.tar.gz](http://mirror.cc.columbia.edu/pub/software/apache/maven/maven-3/3.5.0/binaries/apache-maven-3.5.0-bin.tar.gz)

 

> # tar -xvzf apache-maven-3.5.0-bin.tar.gz -C /usr/local

 

> # cd /usr/local/

 

> # sudo ln -s apache-maven-3.5.0 maven

 

> # vim /etc/profile.d/maven.sh

 

> export M2_HOME=/usr/local/maven

 

> export PATH=${M2_HOME}/bin:${PATH}

 

> #source /etc/profile

 

> #mvn –version

Download tool

> # wget [https://github.com/calfzhou/atlassian-license-study/archive/develop.zip](https://github.com/calfzhou/atlassian-license-study/archive/develop.zip)

> # unzip develop.zip

 

> #cd /opt/jira-license/license-decoder-v2/

 

> # mvn compile

Thay đổi class của file jar

# jar uf /opt/atlassian-jira/atlassian-jira/WEB-INF/lib/atlassian-extras-x.x.x.jar -C /opt/jira-license/license-decoder-v2/target/classes com/atlassian/extras/decoder/v2/Version2LicenseDecoder.class

# jar uf /opt/atlassian-jira/atlassian-jira/WEB-INF/atlassian-bundled-plugins/atlassian-universal-plugin-manager-plugin-x.x.x.jar -C /opt/jira-license/license-decoder-v2/target/classes com/atlassian/extras/decoder/v2/Version2LicenseDecoder.class

Cài đặt thư viện để chạy python

> # yum groupinstall “Development Tools”

 

> # yum install openssl-devel

 

> #curl “https://bootstrap.pypa.io/get-pip.py” -o “get-pip.py”

 

> #python get-pip.py

 

> # pip download M2Crypto

 

> # tar -xvzf M2Crypto-0.26.4.tar.gz

 

> # cd M2Crypto-0.26.4/

 

> # python setup.py build

 

> # python setup.py install

 

> #cd /opt/jira-license/atlassian-keygen

Generate license

> #python generate_dsa_key.py -o mykey.pem

 

> #pip install pyyaml

 

> #cd atlassian-keygen

 

> #vim generate_license.py

Chỉnh dòng 237 như sau: length_bytes = struct.pack(str(‘&gt;L’), license_length)

Sau đó chạy generate key:

> # python generate_license.py -k mykey.pem templates/jira.yml “yourcompany” your-server-id

_Như vậy là bạn đã thực hiện xong phần active Jira, chúc các bạn thành công và sử dụng thử nó, tuy nhiên, nếu bạn là doanh nghiệp và sử dụng Jira cho mục đích ngoài việc học tập thì tuyệt đối không nên làm theo hướng dẫn này, mà hãy trả tiền cho chất xám của họ._

_Nếu bạn đọc hết hướng dẫn này mà vẫn chưa active được, hãy để lại comment, mình sẽ hỗ trợ nhé._

Nhắc lại 1 lần nữa :

A study on license-generating technique for atlassian products. Do *NOT* use for commercial activity.
