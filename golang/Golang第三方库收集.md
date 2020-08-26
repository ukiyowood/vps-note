## 命令行cli
 
#### Cobra
 
`github.com/spf13/cobra`
 
```
func main()  {
    var Version bool
    var rootCMD = &cobra.Command{
        Use: "root {sub}",
        Short: "root command",
        Run: func(cmd *cobra.Command, args []string) {
            fmt.Printf("Inside rootCMD Run with args: %v\n", args)
            if Version {
                fmt.Printf("Version 1.0\n")
            }
        },
    }
    flags := rootCMD.Flags()
    flags.BoolVarP(&Version, "version", "v", false, "Print version info and quit.")
    rootCMD.Execute()
}
```
 
## Web框架
 
#### iris
 
`github.com/kataras/iris`
 
```
func main() {
    app := iris.New()
    app.Get("/", func(c iris.Context) {
        c.JSON("hello world.")
    })
    app.Run(iris.Addr(":8080"))
}
```
 
## SSH库
 
#### crypto/ssh
 
`golang.org/x/crypto/ssh`
 
```
func main()  {
    c, err := ssh.Dial("tcp", "10.10.18.112:22", &ssh.ClientConfig{
        User: "root",
        Auth: []ssh.AuthMethod{ssh.Password("nccloud001")},
        HostKeyCallback: ssh.InsecureIgnoreHostKey(),
    })
    if err != nil {
        log.Fatalf("dial ssh client err: %v\n", err)
    }
    s, err := c.NewSession()
    if err != nil {
        log.Fatalf("get session err: %v\n", err)
    }
    defer s.Close()
    s.Stdout = os.Stdout
    s.Stderr = os.Stderr
    s.Stdin = os.Stdin
    modes := ssh.TerminalModes{
        ssh.ECHO: 0,
        ssh.TTY_OP_OSPEED: 14400,
        ssh.TTY_OP_ISPEED: 14400,
    }
    err = s.RequestPty("linux", 32, 60, modes)
    if err != nil {
        log.Fatalf("get pty err: %v\n", err)
    }
    // Start remote shell
    if err := s.Shell(); err != nil {
        log.Fatal("failed to start shell: ", err)
    }
    if err := s.Wait(); err != nil {
        log.Fatal("failed to return shell: ", err)
    }
}
```
 