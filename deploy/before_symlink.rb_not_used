Chef::Log.info("Creating cron job for the perl scripts")
env = Hash["AWS_ACCESS_KEY_ID" => "#{ node[:deploy]['scripts'][:environment_variables][:AWS_ACCESS_KEY_ID]}", "AWS_SECRET_ACCESS_KEY" => "#{ node[:deploy]['scripts'][:environment_variables][:AWS_SECRET_ACCESS_KEY]}", "REGION" => "#{ node[:deploy]['scripts'][:environment_variables][:REGION]}"]

cron 'test.pl' do
	user'ec2-user'
	minute '*'
	hour '*'
	day '*'
	month '*'
	weekday '*'
	environment env
	command "/opt/perlbrew/perls/perl-5.8.8/bin/perl /tmp/test.pl >> /home/ec2-user/test.pl.log"
	action :create
end
