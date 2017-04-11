FROM centos:6.8
MAINTAINER Keiji Yoshida <keijiyoshida.mail@gmail.com>

RUN yum -y update
RUN yum -y install sudo openssh-server telnet vim

RUN groupadd beringei
RUN useradd beringei -d /home/beringei -g beringei -s /bin/bash
RUN echo "beringei ALL=NOPASSWD: ALL" >> /etc/sudoers

USER beringei

RUN mkdir /home/beringei/.ssh
RUN echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDU+e+kZTtUoWMmW8pt2AvP/u6zmxHjx8e6NsHj9jRZTluV3Q6J0q9r0f4B3DuFo3ZuCA1O/HWxm3GYBY9+gZcCo/NWZWSiScvzMz9ZBBrqRK2iiIt/hne9TX31TkuRN+dWtUc8E+lx4056FYBsjrp0dYxKoxmLabYw6Ho1qzPReWipU3Mp7MNKpaC/U95xS1thrSylQVkBvDRg6V/j2v2qmptw6Df+FNp65gtjacxFWfCcUfH8VuwOz6eb5Ve9Bc3Mlfu34ODLy6VnJIvh0Kmhbisx1AYOXZLCaKa0l8qUhNso21YgDNeZtegibO07XgO8q7oYr1tSoYA/d5bMqO0d beringei@localhost" > /home/beringei/.ssh/authorized_keys
RUN chmod 600 /home/beringei/.ssh/authorized_keys

USER root

CMD /sbin/service sshd start && tail -f /dev/null
