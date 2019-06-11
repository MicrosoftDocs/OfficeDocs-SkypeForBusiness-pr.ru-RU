---
title: 'Lync Server 2013: контрольный список развертывания для конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Контрольный список развертывания для конференц-связи с телефонным подключением в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-10-03_

Компоненты, необходимые для конференц-связи с телефонным подключением, развертываются при развертывании рабочей нагрузки Конференции. Прежде чем настраивать конференц-связь с телефонным подключением, вам нужно развернуть либо корпоративный голосовой, либо сервер-посредник, а также коммутируемый шлюз для коммутируемой телефонной сети.

Чтобы присоединиться к звуковой или видеоконференции, необходимо выполнить все действия, описанные в приведенной ниже таблице, прежде чем пользователи смогут звонить с помощью PSTN.

<div>


> [!NOTE]  
> При переходе с Office Communications Server 2007 R2 необходимо установить последние обновления для среды Office Communications Server 2007 R2, прежде чем развертывать Конференц-связь с телефонным подключением.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Процесс развертывания конференц-связи с телефонным подключением

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Шаги</th>
<th>Разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Создание топологии, включающей рабочую нагрузку для конференций, в том числе сервер-посредник и шлюз PSTN, а также развертывание пула переднего плана или сервера Standard Edition</strong></p></td>
<td><ol>
<li><p>Запустите построитель топологии, чтобы настроить топологию. При настройке топологии выберите вариант конференц-связи с телефонным подключением.</p></li>
<li><p>Опубликуйте топологию и разверните пул переднего плана или сервер Standard Edition.</p></li>
<li><p>При необходимости создайте изолированный сервер-посредник и свяжите его с шлюзом PSTN.</p>
<div>

> [!NOTE]  
> Этот этап необходим только в том случае, если вы не разворачиваете корпоративный голосовой стандарт и не разместите его на сервере Enterprise Едитионфронт End Server или Standard Edition. При развертывании Enterprise Voice вы устанавливаете и настраиваете серверы исправлений и шлюзы PSTN в рамках развертывания Enterprise Voice. Если вы настроили сервер из организатора, вы устанавливаете и настроите сервер исправлений как часть пула переднего плана или развертывания сервера Standard Edition.


</div></li>
</ol></td>
<td><p>Администраторы домена</p>
<p>RTCUniversalServerAdmins</p>
<p>Администратор</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></p></li>
<li><p>Создание пула серверов с изолированными исправлениями: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">развертывание серверов обновлений и определение одноранговых узлов в Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial plans</strong></p></td>
<td><p>Абонентская группа — это набор правил нормализации телефонных номеров, которые преобразуют телефонные номера, набранные из определенного местонахождения, в единый стандартный формат (E.164) для авторизации телефона и маршрутизации вызова. Один и тот же телефонный номер, набранный в разных местонахождениях, может на основе соответствующих абонентских групп преобразовываться в разные номера E.164, в зависимости от местонахождения. Если вы выполняете развертывание корпоративной голосовой связи, вы настраиваете абонентские группы в рамках этого развертывания, и вам нужно убедиться, что абонентские группы также должны поддерживать Конференц-связь с телефонным подключением. Если вы не разворачиваете корпоративный голосовой телефон, вам нужно настроить абонентские группы для конференц-связи с телефонным подключением.</p>
<p>Настройте абонентские группы с помощью панели управления Lync Server 2013 или командной консоли Lync Server Management Shell, как описано ниже.</p>
<ol>
<li><p>Создайте одну или несколько абонентских групп для маршрутизации доступа по телефонной линии телефонных номеров.</p></li>
<li><p>Назначьте каждому пулу абонентскую группу по умолчанию. Задайте для параметра <strong>Регион конференц-связи с телефонным подключением</strong> географическое расположение, которому соответствует эта абонентская группа. Регион связывает абонентскую группу с номерами доступа по телефонной линии.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Убедитесь, что абонентским группам назначены регионы</strong></p></td>
<td><p>Выполните командлеты <strong>Get-CsDialPlan</strong> и <strong>Set-CsDialPlan</strong>, чтобы убедиться в наличии назначенных регионов у всех абонентских групп.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Проверка абонентских планов Lync Server 2013 назначенные регионы</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Проверка или изменение требований персонального идентификационного номера (ПИН-кода) пользователя (необязательно)</strong></p></td>
<td><p>С помощью панели управления Lync Server 2013 или командной консоли Lync Server Management Shell вы можете просмотреть или изменить <strong>политику ПИН-кода</strong>для конференций. You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Проверка параметров политики ПИН-кодов в Lync Server 2013 (необязательно)</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Настройка политики конференц-связи для поддержки конференц-связи с телефонным подключением</strong></p></td>
<td><p>Настройте параметры <strong>политики Конференц</strong> -связи с помощью панели управления lync Server 2013 или командной консоли Lync Server Management Shell. Specify whether:</p>
<ul>
<li><p>Разрешено ли телефонное подключение к конференции в ТСОП.</p></li>
<li><p>Могут ли пользователи приглашать анонимных участников.</p></li>
<li><p>Могут ли непроверенные пользователи присоединяться к конференции с помощью телефонного подключения. При присоединении с обратным звонком сервер конференций звонит пользователю, и пользователь отвечает по телефону, чтобы присоединиться к конференции.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Настройка политики конференц-связи с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial-in access numbers</strong></p></td>
<td><p>С помощью панели управления Lync Server 2013 или командной консоли Lync Server Management Shell вы можете настроить номера доступа для телефонного подключения, которые пользователи смогут использовать для подключения к Конференции, и указать регионы, связывающие номер доступа с соответствующими абонентской абонентской группы. The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation. Все номера доступа доступны на странице параметров конференц-связи с телефонным подключением.</p>
<div>

> [!NOTE]  
> Создав номера доступа для телефонного подключения, вы можете использовать командлет <STRONG>Set-ксдиалинконференЦингакцесснумбер</STRONG> , чтобы изменить отображаемое имя объектов контакта Active Directory, чтобы пользователи могли легко определить правильный номер доступа.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Проверка параметров конференц-связи с телефонным подключением (необязательно)</strong></p></td>
<td><p>Командлет <strong>Get-CsDialinConferencingAccessNumber</strong> используется для поиска абонентских групп, имеющим регион конференц-связи с телефонным подключением, который не используется ни одним номером доступа, а также найдите номера доступа, которым не назначен регион.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Проверка параметров конференц-связи с телефонным подключением в Lync Server 2013 (необязательно)</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Изменение сопоставления клавиш для команд DTMF (необязательно)</strong></p></td>
<td><p>Используйте командлет <strong>Set-ксдиалинконференЦингдтмфконфигуратион</strong> , чтобы изменить ключи, используемые для команд с двумя сигналами многочастотной связи (DTMF), которые могут использоваться участниками для управления параметрами конференции (например, отключение и включение и отключение звукового и разблокирования).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Изменение назначенных клавиш для команд DTMF в Lync Server 2013 (необязательно)</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Изменение поведения оповещений о присоединении к конференции и выходе из нее (необязательно)</strong></p></td>
<td><p>Командлет <strong>Set-CsDialinConferencingConfiguration</strong> используется для изменения порядка работы оповещений, когда участники присоединяются к конференции или покидают ее.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013 (необязательно)</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Проверка конференц-связи с телефонным подключением (необязательно)</strong></p></td>
<td><p>Командлет <strong>Test-CsDialInConferencing</strong> используется для проверки правильности работы номеров доступа для указанного пула.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Проверка конференц-связи с телефонным подключением в Lync Server 2013 (необязательно)</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Развертывание надстройки собраний по сети для Lync 2013</strong></p></td>
<td><p>Разверните надстройку "собрание по сети" для Lync 2013, чтобы пользователи могли планировать конференции, поддерживающие Конференц-связь с телефонным подключением. Надстройка "собрание по сети" для Lync 2013 устанавливается автоматически при установке Lync 2013.</p></td>
<td><p>Администраторы</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Развертывание надстройки собраний по сети для Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Настройка параметров учетных записей пользователей</strong></p></td>
<td><p>С помощью панели управления Lync Server 2013 или командной консоли Lync Server Management Shell можно настроить <strong>универсальный код ресурса</strong> телефонной линии как уникальный, нормализованный номер телефона (например, Tel: + 14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Настройка параметров учетных записей пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка каталогов конференций (рекомендуется)</p></td>
<td><p>Командлет <strong>New-CsConferenceDirectory</strong> используется для создания одного каталога конференции для каждых 999 пользователей в пуле.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Требования к конференц-связи с телефонным подключением в Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Рекомендуется) создание каталогов конференций</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Приглашение пользователей принять участие в конференц-связи с телефонным подключением и установка начальных ПИН-кодов (необязательно)</strong></p></td>
<td><p>С помощью сценария <strong>Set-кспинсендкавелкомемаил</strong> настройте начальные контакты пользователей и отправьте приветственное сообщение с начальным PIN-кодом и ссылкой на страницу параметров конференц-связи с телефонным подключением.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Приветствие пользователей в конференции с телефонным подключением Lync Server 2013 (необязательно)</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

