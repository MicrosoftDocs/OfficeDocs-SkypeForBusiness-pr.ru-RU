---
title: 'Lync Server 2013: процесс развертывания для парковки вызовов'
description: 'Lync Server 2013: процесс развертывания для парковки вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 149252d39ba3fc0c552900c87e453c60e1651a08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575715"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Процесс развертывания для парковки вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-25_

В этом разделе представлен обзор действий, необходимых для развертывания приложения парковки вызовов. Перед настройкой парковки вызовов необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью. Компоненты, необходимые для парковки вызовов, устанавливаются и включаются при развертывании корпоративной голосовой связи.

### <a name="call-park-deployment-process"></a>Процесс развертывания парковки вызовов

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
<th>Необходимые группы и роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка диапазонов орбит парковки вызовов в таблице орбит</p></td>
<td><p>С помощью панели управления Lync Server или командлета <strong>New – CSCallParkOrbit</strong> создайте Диапазоны орбит в таблице орбит парковки вызовов и свяжите их со службой приложения, в которой размещается приложение парковки вызовов.</p>
<div>

> [!NOTE]  
> Для простой интеграции с существующими абонентскими группами диапазоны орбит обычно настраиваются как блок виртуальных расширений. Назначение номеров DID как номеров орбит в таблице орбит парковки вызовов не поддерживается.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка параметров приостановки звонков</p></td>
<td><p>Используйте командлет <strong>Set – CsCpsConfiguration</strong> для настройки параметров парковки вызовов. Рекомендуется настроить параметр <strong>OnTimeoutURI</strong> для настройки резервного назначения для использования при истечении времени ожидания приостановленного вызова. Кроме того, можно настроить следующие параметры:</p>
<ul>
<li><p><strong>EnableMusicOnHold</strong> для включения и выключения музыки при удержании вызова (необязательный параметр);</p></li>
<li><p><strong>MaxCallPickupAttempts</strong> для определения количества ответных звонков припаркованным вызовом в адрес отвечающего телефона до переадресации звонка на резервный URI (необязательный параметр);</p></li>
<li><p><strong>CallPickupTimeoutThreshold</strong> для определения времени между парковкой вызова и вызовом телефонного номера, по которому на вызов был получен ответ (необязательный параметр);</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Настройка параметров парковки вызовов в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Можно настроить музыку при удержании (необязательно)</p></td>
<td><p>Используйте командлет <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> для настройки и загрузки аудиофайла, если вы не хотите использовать стандартную музыку при удержании.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Настройка музыки парковки вызовов на удержании в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка политики голосовой связи для включения парковки вызовов для пользователей</p></td>
<td><p>Используйте панель управления Lync Server или командлет <strong>Set – CSVoicePolicy</strong> с параметром <strong>enablecallpark задано</strong> , чтобы включить приостановку вызовов для пользователей в политике голосовой связи.</p>
<div>

> [!NOTE]  
> По умолчанию парковки вызовов отключен для всех пользователей.


</div>
<div>

> [!NOTE]  
> При наличии нескольких политик голосовой связи убедитесь в том, что свойство EnableCallPark задано для каждой политики голосовой связи, а не только для политики по умолчанию.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Включение парковки вызовов для пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка правил нормализации для приостановки звонков</p></td>
<td><p>Орбиты парковки вызовов не требуют нормализации. Убедитесь, что правила нормализации не включают ваши диапазоны орбиты. При необходимости создайте дополнительные правила нормализации для блокирования нормализации орбит.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Проверка правил нормализации для парковки вызовов в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Проверка развертывания парковки вызовов</p></td>
<td><p>Проверка парковки и получение вызовов убедитесь, что конфигурация работает должным образом.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Необязательно Проверка развертывания парковки вызовов в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

