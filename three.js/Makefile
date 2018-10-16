.PHONY: build
build:
	(cd src/threex/threex-aruco && make build)
	echo	> build/ar.js
	cat 	vendor/jsartoolkit5/build/artoolkit.min.js	\
		vendor/jsartoolkit5/js/artoolkit.api.js		>> build/ar.js
	cat	vendor/signals.min.js				>> build/ar.js
	cat	src/threex/*.js					\
		src/new-api/*.js 				\
		src/markers-area/*.js 				>> build/ar.js
	echo "export { THREEx };"               >> build/ar.js

watch: build
	fswatch -0 src/*/*.js | xargs -0 -n 1 -I {} make build
