![mahua](mahua-logo.jpg)
#DOL
##Description
�ֲ�ʽ�����㣨DOL����һ�����������ܱ�̲���Ӧ�ó���DOL����ָ���Ļ����ϼ���Ŀ�����������ģ��Ӧ�ó���͹��ܵĻ����ϵ�SystemCģ�����档���⣬DOL�ṩ��һ������XML�Ĺ淶��ʽ��������һ���ദ����ϵͳ�������󶨺�ӳ�䲢��Ӧ�ó����ִ�С�
#Install
###Ubuntu�����úñ�Ҫ�Ļ���

$ sudo apt-get update

$ sudo apt-get install ant

$ sudo apt-get install openjdk-7-jdk

$ sudo apt-get install unzip

###�����ļ�

$ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz

$ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip

###��ѹ�ļ�

1.�½�dol�ļ�

$ mkdir dol 2.��dolethz.zip��ѹ�� dol�ļ�����

$ unzip dol_ethz.zip -d dol 3.��ѹsystemc

$ tar -zxvf systemc-2.3.1.tgz

###����systemc

1.��ѹ�����systemc-2.3.1��Ŀ¼��

$ cd systemc-2.3.1 2.�½�һ����ʱ�ļ���objdir

$ mkdir objdir 3.������ļ���objdir

$ cd objdir 4.����configure���ܸ���ϵͳ�Ļ�������һ�²��������ڱ��룩

$ ../configure CXX=g++ --disable-async-updates

###5.����

$ sudo make install

6.��¼��ǰ�Ĺ���·�����������ǰ����·�������������������ã�

$ pwd

###����DOL

1.����ոյ�dol�ļ��У��޸�build.xml�ļ� �ҵ�������λ�������˵��������systemcλ��������

property name=��systemc.inc�� value=��YYY/include�� property name=��systemc.lib�� value=��YYY/lib-linux/libsystemc.a��/ ��YYY�ĳ���ҳpwd�Ľ����ע�⣬���� 64λ ϵͳ�Ļ�����lib-linuxҪ�ĳ�lib-linux64��

2.����

$ ant -f build_zip.xml all ���ɹ�����ʾbuild sucessful

3.���е�һ�����ӽ���build/bin/main·����

$ cd build/bin/main

4.Ȼ�����е�һ������

$ ant -f runexample.xml -Dnumber=1

##Experimental experience
���ε�ʵ��ʱDOL������ʵ�飬ta�����������еĲ������裬����ֻ��Ҫ����ɵ��ʽ�Ĳ��������ˣ������ϲ��Ǻ��ѡ�������ʵ������޸�build.xml�ļ���ʱ���ҵ��������64λ�ģ������޸ĵ�ʱ����Ҫ���������Ϣ��Ϊ32λ�Ĳ��ܵõ����ս�������Ҳ�Ǻ�����ta��֪���ģ������˺ܳ�ʱ�䡣�ܵ���˵�˴ε�ʵ����Բ���ģ��ջ�޴�