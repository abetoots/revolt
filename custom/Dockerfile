ARG ols_version
ARG lsphp_version
FROM litespeedtech/openlitespeed:${ols_version}-${lsphp_version}
#https://docs.docker.com/engine/reference/builder/#understand-how-arg-and-from-interact
ARG lsphp_version
ARG php_version
# follow ols way to add php extensions https://docs.litespeedtech.com/extapp/php/extensions/
RUN apt update && apt install ${lsphp_version}-pear -y && \
    #install xdebug using pecl but using OSL's way
    /usr/local/lsws/${lsphp_version}/bin/pecl install xdebug \
    #get xdebug directory and append it as zend_extension to our php.ini using output redirection
    # echo "zend_extension=$(/usr/local/lsws/${lsphp_version}/bin/pear config-get ext_dir)/xdebug.so" >> /usr/local/lsws/${lsphp_version}/etc/php/${php_version}/litespeed/php.ini && \
    # echo "xdebug.mode = debug" >> /usr/local/lsws/${lsphp_version}/etc/php/${php_version}/litespeed/php.ini && \
    # echo "xdebug.start_with_request = yes" >> /usr/local/lsws/${lsphp_version}/etc/php/${php_version}/litespeed/php.ini && \
    # echo "xdebug.client_port = 9000" >> /usr/local/lsws/${lsphp_version}/etc/php/${php_version}/litespeed/php.ini && \