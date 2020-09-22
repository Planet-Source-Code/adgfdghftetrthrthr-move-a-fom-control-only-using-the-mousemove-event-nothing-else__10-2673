<div align="center">

## Move a Fom/Control ONLY using the MouseMove Event, Nothing Else\!


</div>

### Description

Ive, done it, hehhee
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[adgfdghftetrthrthr](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/adgfdghftetrthrthr.md)
**Level**          |Beginner
**User Rating**    |5.0 (25 globes from 5 users)
**Compatibility**  |VB\.NET
**Category**       |[Controls/ Forms/ Dialogs/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-dialogs-menus__10-3.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/adgfdghftetrthrthr-move-a-fom-control-only-using-the-mousemove-event-nothing-else__10-2673/archive/master.zip)





### Source Code

```
'Example code.
  Private Sub Form1_MouseMove(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles MyBase.MouseMove
    MouseDragging(e, Me)
  End Sub
  Private Sub Button1_MouseMove(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseMove
    MouseDragging(e, Me.Button1)
  End Sub
  'Copyright Andrew Vos 2004 :)
  Private Sub MouseDragging(ByVal e As MouseEventArgs, ByVal Control As Control)
    Static OldPosition As New Point(-1, -1)
    If Not (e.Button = Nothing) Then
      If e.Button = MouseButtons.Left Then
        If (OldPosition.X = -1) And (OldPosition.Y = -1) Then OldPosition = New Point(e.X, e.Y)
        If e.Y <> OldPosition.Y Then
          Control.Top += e.Y - OldPosition.Y 'move Up/Down
        End If
        If e.X <> OldPosition.X Then
          Control.Left += e.X - OldPosition.X 'move Left/Right
        End If
      End If
    Else
      'button is nothing, maybe it was lifted.
      OldPosition = New Point(-1, -1)
    End If
  End Sub
```

