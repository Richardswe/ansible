# Generate the hash locally 
shell: python -c "from passlib.hash import sha512_crypt; import getpass; print sha512_crypt.encrypt(getpass.getpass())"
Password:
$6$rounds=656000$nv6b5eRCf0MA3Uth$YLcyFUT63rTMB8crCejv5IdyOYIpv62l5FVt.jjw4cNuqPX8HyYwmx/w48SFq/LJtYLrEV92mje7jV0Nfm/9g0