### Thư mục chứa file backup trên server backuppc

```sh
cd /var/lib/backuppc/pc
```

### Thay đổi user thực hiện rsync khi sử dụng ssh-key-coppy không phải `root`:

- Tìm và thay đổi lại thông tin của 2 command bên dưới , ví dụ ở đây khi thay đổi tài khoản từ root sang backuppc

```sh
#$Conf{RsyncClientCmd} = '$sshPath -q -x -l root $host $rsyncPath $argList+';
$Conf{RsyncClientCmd} = '$sshPath -q -x -l backuppc $host $rsyncPath $argList+';

# Comment out these line and add the same line with root user changed to backuppc
#$Conf{RsyncClientRestoreCmd} = '$sshPath -q -x -l root $host $rsyncPath $argList+';
```

