## Part I. 클러터-GTK 액터, 객체 ##

### 객체 계층도 ###

GObject<br/>
&nbsp;&nbsp;GInitiallyUnowned<br/>
&nbsp;&nbsp;&nbsp;&nbsp;ClutterActor<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[GtkClutterActor](./chap2.markdown#gtkclutteractor)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ClutterTexture<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkClutterTexture<br/>
&nbsp;&nbsp;&nbsp;&nbsp;GtkWidget<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkContainer<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[GtkClutterEmbed](./chap2.markdown#gtkclutterembed)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkBin<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GtkWindow<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[GtkClutterWindow](./chap2.markdown#gtkclutterwindow)


### 객체 색인 ###

<table border="0">
<tr><td width="33%"> ClutterActor                                        </td><td width="33%"> ClutterTexture    </td><td width="34%"> GInitiallyUnowned                                     </td></tr>
<tr><td>             GObject                                             </td><td>             GtkBin            </td><td>             <a href="./chap2.markdown#gtkclutteractor">GtkClutterActor</a>   </td></tr>
<tr><td>             <a href="./chap2.markdown#gtkclutterembed">GtkClutterEmbed</a> </td><td>             GtkClutterTexture </td><td>             <a href="./chap2.markdown#gtkclutterwindow">GtkClutterWindow</a></td></tr>
<tr><td>             GtkContainer                                        </td><td>             GtkWidget         </td><td>             GtkWindow                                             </td></tr>
</table>
