---
title: Контрольный список развертывания Lync Server 2013 для конференц-связи с телефонным подключением
description: Сервер Lync Server 2013 контрольный список развертывания для конференц-связи с телефонным подключением.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 743b5120bf011ab8467679bea9869a46231b0835
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568365"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Контрольный список развертывания для конференц-связи с телефонным подключением в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-10-03_

Компоненты, необходимые для конференц-связи с телефонным подключением, разворачиваются при развертывании рабочей нагрузки конференц-связи. Перед настройкой конференц-связи с телефонным подключением необходимо выполнить развертывание корпоративной голосовой или сервер-посредника и шлюза телефонной сети общего пользования (PSTN).

Перед тем как пользователи смогут присоединяться к аудио- или видеоконференции из ТСОП, необходимо выполнить все действия, приведенные в следующей таблице.

<div>


> [!NOTE]  
> При переходе с Office Communications Server 2007 R2 необходимо установить последние обновления для среды Office Communications Server 2007 R2 перед развертыванием конференц-связи с телефонным подключением.



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
<th>Действия</th>
<th>Разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Создание топологии, включающей рабочую нагрузку конференц-связи, включая сервер-посредник и шлюз PSTN, а также развертывание пула переднего плана или сервера Standard Edition</strong></p></td>
<td><ol>
<li><p>Запустите построитель топологий для настройки топологии. При настройке топологии выберите вариант конференц-связи с телефонным подключением.</p></li>
<li><p>Опубликуйте топологию и разверните пул переднего плана или сервер Standard Edition.</p></li>
<li><p>При необходимости создайте изолированный сервер-посредник и свяжите его с шлюзом PSTN.</p>
<div>

> [!NOTE]  
> Этот шаг необходим только в том случае, если вы не развертываете корпоративную голосовую связь и не размещаете сервер-посредник с помощью сервера Enterprise Едитионфронт или сервера Standard Edition. При развертывании корпоративной голосовой связи вы устанавливаете и настраиваете серверы-посредники и шлюзы PSTN в рамках развертывания корпоративной голосовой связи. При совместном размещении сервера-посредника устанавливается и настраивается сервер-посредник в составе пула переднего плана или развертывания сервера Standard Edition.


</div></li>
</ol></td>
<td><p>Администраторы домена</p>
<p>RTCUniversalServerAdmins</p>
<p>Администратор</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></p></li>
<li><p>Создание изолированного пула серверов-посредников: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Настройка абонентских групп</strong></p></td>
<td><p>Абонентская группа — это набор правил нормализации телефонных номеров, которые преобразуют телефонные номера, набранные из определенного местонахождения, в единый стандартный формат (E.164) для авторизации телефона и маршрутизации вызова. Один и тот же телефонный номер, набранный в разных местонахождениях, может на основе соответствующих абонентских групп преобразовываться в разные номера E.164, в зависимости от местонахождения. При развертывании корпоративной голосовой связи вы настраиваете абонентские группы в рамках этого развертывания и должны быть уверены, что абонентские группы также должны поддерживать Конференц-связь с телефонным подключением. Если вы не развертываете корпоративную голосовую связь, необходимо настроить абонентские группы для конференц-связи с телефонным подключением.</p>
<p>Настройте абонентские группы с помощью панели управления Lync Server 2013 или Командная консоль Lync Server, как показано ниже.</p>
<ol>
<li><p>Создайте одну или несколько абонентских групп для маршрутизации доступа по телефонной линии телефонных номеров.</p></li>
<li><p>Назначьте каждому пулу абонентскую группу по умолчанию. Установите в параметре <strong>Dial-in conferencing region (Регион конференц-связи с телефонным подключением)</strong> географическое расположение, которому соответствует эта абонентская группа. Регион связывает абонентскую группу с номерами доступа по телефонной линии.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Настройка абонентских планов для конференц-связи с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Убедитесь, что абонентским группам назначены регионы</strong></p></td>
<td><p>Выполните командлеты <strong>Get – CsDialPlan</strong> и <strong>Set – CsDialPlan</strong> , чтобы убедиться, что для всех абонентских абонентов назначен регион.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Убедитесь, что в телефонных планах Lync Server 2013 назначены регионы</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Проверка или изменение требований персонального идентификационного номера (ПИН-кода) пользователя (необязательно)</strong></p></td>
<td><p>Используйте панель управления Lync Server 2013 или командную консоль Lync Server для просмотра или изменения <strong>политики ПИН-кодов</strong>для конференц-связи. Можно задать минимальную длину ПИН-кода, максимальное количество попыток входа, истечение срока действия ПИН-кода, а также указать, разрешены ли общие шаблоны.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Необязательно Проверка параметров политики ПИН-кода в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Настройка политики конференц-связи для поддержки конференц-связи с телефонным подключением</strong></p></td>
<td><p>Настройте параметры <strong>политики Конференц</strong> -связи с помощью панели управления lync Server 2013 или консоли управления Lync Server. Укажите следующее.</p>
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
<td><p><strong>Настройка номеров доступа по телефонной линии</strong></p></td>
<td><p>Используйте панель управления Lync Server 2013 или командную консоль Lync Server, чтобы настроить номера доступа для телефонного подключения, вызываемые пользователями для связи с Конференцией, и указать регионы, которые связывают номер доступа с соответствующими абонентской абонентской настройкой. Первые три номера доступа для региона, указанные абонентской группой организатора, включаются в приглашение на конференцию. Все номера доступа доступны на странице параметров конференц-связи с телефонным подключением.</p>
<div>

> [!NOTE]  
> После создания номеров доступа для телефонного подключения можно использовать командлет <STRONG>Set – CsDialInConferencingAccessNumber</STRONG> , чтобы изменить отображаемое имя контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Проверка параметров конференц-связи с телефонным подключением (необязательно)</strong></p></td>
<td><p>С помощью командлета <strong>Get-CsDialinConferencingAccessNumber</strong> найдите абонентские группы, имеющие регион конференц-связи с телефонным подключением, который не используется ни одним номером доступа, а также найдите номера доступа, которым не назначен регион.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Необязательно Проверка параметров конференц-связи с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Изменение сопоставления клавиш для команд DTMF (необязательно)</strong></p></td>
<td><p>С помощью командлета <strong>Set-CsDialinConferencingDtmfConfiguration</strong> измените сочетания клавиш, используемые для команд тонального набора (DTMF), которые могут использоваться участниками для управления параметрами конференции (такими как отключение и включение звука или блокировка и разблокировка).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Необязательно Изменение сопоставления клавиш для команд DTMF в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Изменение функциональности присоединения к конференции и передачи оповещений (необязательно)</strong></p></td>
<td><p>С помощью командлета <strong>Set-CsDialinConferencingConfiguration</strong> измените порядок работы оповещений, когда участники присоединяются к конференции или покидают ее.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Необязательно Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Проверка конференц-связи с телефонным подключением (необязательно)</strong></p></td>
<td><p>С помощью командлета <strong>Test-CsDialInConferencing</strong> протестируйте правильность работы номеров доступа для указанного пула.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Необязательно Проверка конференц-связи с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Развертывание надстройки собраний по сети для Lync 2013</strong></p></td>
<td><p>Разверните надстройку "собрание по сети" для Lync 2013, чтобы пользователи могли планировать конференции, поддерживающие Конференц-связь с телефонным подключением. Надстройка "собрание по сети" для Lync 2013 устанавливается автоматически при установке Lync 2013.</p></td>
<td><p>Администраторы</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Развертывание надстройки собраний по сети для Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Настройка параметров учетных записей пользователей</strong></p></td>
<td><p>С помощью панели управления Lync Server 2013 или командной консоли Lync Server настройте <strong>универсальный код ресурса (URI)</strong> телефонной линии в качестве уникального нормализованного номера телефона (например, Tel: + 14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Настройка параметров учетных записей пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Предложен Настройка каталогов конференций</p></td>
<td><p>Используйте командлет <strong>New-CsConferenceDirectory</strong> для создания одного каталога конференций для каждых 999 пользователей в пуле.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Требования к конференц-связи с телефонным подключением в Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(рекомендуется) создание каталогов конференций</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Приглашение пользователей принять участие в конференц-связи с телефонным подключением и установка начальных ПИН-кодов (необязательно)</strong></p></td>
<td><p>С помощью скрипта <strong>Set-CsPinSendCAWelcomeMail</strong> установите начальные ПИН-коды пользователей и отправьте приветственное сообщение, содержащее начальный ПИН-код и ссылку на страницу параметров конференц-связи с телефонным подключением.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Необязательно Добро пожаловать в Конференц-связь с телефонным подключением в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

