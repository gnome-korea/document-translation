## Part I. 클러터-GTK 액터, 객체 ##

### 객체 계층도 ###

<pre>
GObject<br/>
&nbsp;&nbsp;GInitiallyUnowned<br/>
&nbsp;&nbsp;&nbsp;&nbsp;ClutterActor<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[GtkClutterActor](./chap2.markdown#gtkclutteractor)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ClutterTexture
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkClutterTexture
&nbsp;&nbsp;&nbsp;&nbsp;GtkWidget
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkContainer
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[GtkClutterEmbed](./chap2.markdown#gtkclutterembed)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkBin
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkWindow
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[GtkClutterWindow](./chap2.markdown#gtkclutterwindow)

### 객체 색인 ###

<table border="0">
<tr><td width="33%"> ClutterActor                                        </td><td width="33%"> ClutterTexture    </td><td width="34%"> GInitiallyUnowned                                     </td></tr>
<tr><td>             GObject                                             </td><td>             GtkBin            </td><td>             [GtkClutterActor](./chap2.markdown#gtkclutteractor)   </td></tr>
<tr><td>             [GtkClutterEmbed](./chap2.markdown#gtkclutterembed) </td><td>             GtkClutterTexture </td><td>             [GtkClutterWindow](./chap2.markdown#gtkclutterwindow) </td></tr>
<tr><td>             GtkContainer                                        </td><td>             GtkWidget         </td><td>             GtkWindow                                             </td></tr>
</table>
