FROM centos:centos7.7.1908

RUN yum check-update; \
   yum install -y gcc libffi-devel python-devel openssl-devel epel-release; \
   yum install -y python-pip python-wheel; \
   yum install -y openssh-clients; \
   curl https://packages.microsoft.com/config/rhel/7/prod.repo | tee /etc/yum.repos.d/microsoft.repo; \
   yum install -y powershell; \
   pwsh -c "Set-PackageSource -Name PSGallery -Trusted"; \
   pwsh -c "Install-Module AZ -Scope AllUsers"; \
   pip install --upgrade pip

RUN  pip install ansible[azure]