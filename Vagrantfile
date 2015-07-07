Vagrant.configure("2") do |config|
  config.vm.box = "xcoo/trusty64"

  config.vm.provider :aws do |aws, override|
    aws.access_key_id = ENV['AWS_ACCESS_KEY']
    aws.secret_access_key = ENV['AWS_SECRET_KEY']
    #aws.session_token = "SESSION TOKEN"
    aws.keypair_name = ENV['AWS_KEYPAIR']

    aws.ami = "ami-7747d01e"
    aws.instance_type = "c3.4xlarge"
    override.ssh.username = "vagrant"
    override.ssh.private_key_path = ENV['AWS_SSH_PRIVATE_KEY']
    aws.block_device_mapping = [{ 'DeviceName' => '/dev/sda1', 'Ebs.VolumeSize' => 100 }]
    aws.tags = {
      'Name' => 'travis-worker-vagrant-trusty',
    }
  end
end
