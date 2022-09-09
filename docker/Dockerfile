#
# dockerfile for pmemhackathon, fc30 based
#
# Note: After making any changes to files within this directory you have to rebuild
#       the image:
#
# $ sudo docker build -t pmemhackathon/pmemfc30:09 -f ./docker/Dockerfile ./docker/
#

FROM fedora:30

LABEL maintainer="andy.rudoff@intel.com"

ENV RPMA_DEPS "\
	iproute \
	iputils \
	librdmacm-utils \
	net-tools \
	rdma-core-devel"

RUN dnf update -y && dnf install -y\
	$RPMA_DEPS\
	autoconf\
	automake\
	bash-completion\
	bc\
	bind-utils\
	binutils\
	clang\
	cmake\
	daxctl-devel\
	doxygen\
	emacs\
	file\
	findutils\
	fuse\
	fuse-devel\
	gcc\
	gcc-c++\
	gdb\
	git-all\
	glib2-devel\
	golang\
	lbzip2\
	libatomic\
	libtool\
	libudev-devel\
	libunwind-devel\
	make\
	man\
	memkind\
	memkind-devel\
	nano\
	ncurses-devel\
	ndctl-devel\
	numactl-devel\
	java-1.8.0-openjdk\
	openssh-server\
	pandoc\
	passwd\
	perl-Text-Diff\
	pkgconfig\
	python3-devel\
	rapidjson-devel\
	rpm-build\
	rpm-build-libs\
	rpmdevtools\
	rsync\
	ruby-devel\
	strace\
	tar\
	tbb-devel\
	unzip\
	vim-enhanced\
	wget\
	which\
	xmlto\
	xmvn

COPY pmdk.sh /
RUN /pmdk.sh

COPY librpma.sh /
RUN /librpma.sh
