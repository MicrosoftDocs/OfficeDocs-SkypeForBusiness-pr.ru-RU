---
title: 'Lync Server 2013: процесс развертывания для парковки звонков'
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
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Процесс развертывания для парковки звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-25_

В этом разделе приводятся общие сведения о том, как развернуть приложение для парковки звонков. Перед настройкой приостановки звонка необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью. Компоненты, необходимые для парковки звонков, устанавливаются и включаются при развертывании корпоративной голосовой связи.

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
<th>Шаги</th>
<th>Необходимые группы и роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка диапазонов орбит парковки вызовов в таблице орбит</p></td>
<td><p>С помощью панели управления Lync Server или командлета <strong>New-кскаллпаркорбит</strong> создайте диапазоны на орбите в таблице с приостановкой на орбиту и свяжите их со службой приложения, на которой размещается приложение для приостановки звонков.</p>
<div>

> [!NOTE]  
> Для простой интеграции с существующими абонентскими группами диапазоны орбит обычно настраиваются как блок виртуальных расширений. Назначение номеров DID как номеров орбит в таблице орбит парковки вызовов не поддерживается.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Создание или изменение диапазона орбиты на расстоянии вверх на сервере Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка параметров парковки вызовов</p></td>
<td><p>Используйте командлет <strong>Set-кскпсконфигуратион</strong> , чтобы настроить параметры парковки звонков. Рекомендуется настроить параметр <strong>онтимеаутури</strong> для настройки резервного назначения для использования по истечении времени ожидания звонка. Вы также можете настроить следующие параметры:</p>
<ul>
<li><p><strong>EnableMusicOnHold</strong> для включения и выключения музыки при удержании вызова (необязательный параметр).</p></li>
<li><p><strong>MaxCallPickupAttempts</strong> для определения количества ответных звонков для припаркованных вызовов в адрес отвечающего телефона перед переадресацией звонка на резервный URI (необязательный параметр).</p></li>
<li><p><strong>CallPickupTimeoutThreshold</strong> для определения времени между парковкой вызова и вызовом телефонного номера, по которому на вызов был получен ответ (необязательный параметр).</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Настройка параметров парковки звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Можно настроить музыку при удержании (необязательно)</p></td>
<td><p>Используйте командлет <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> для настройки и загрузки аудиофайла, если вы не хотите использовать стандартную музыку при удержании.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Настройка музыкального сопровождения для приема звонков на удержании в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка политики голосовой связи для поддержки приостановки звонков для пользователей</p></td>
<td><p>С помощью панели управления Lync Server или командлета <strong>Set-ксвоицеполици</strong> с параметром <strong>енаблекаллпарк</strong> , чтобы включить приостановку звонков для пользователей в политике голосовой связи.</p>
<div>

> [!NOTE]  
> По умолчанию приостановление звонков для всех пользователей отключено.


</div>
<div>

> [!NOTE]  
> При наличии нескольких политик голосовой связи убедитесь в том, что свойство EnableCallPark задано для каждой политики голосовой связи, а не только для политики по умолчанию.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Включение приостановки звонков для пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка правил нормализации для парковки вызовов</p></td>
<td><p>Орбиты парковки вызовов не требуют нормализации. Убедитесь, что правила нормализации не включают ваши диапазоны орбиты. При необходимости создайте дополнительные правила нормализации для блокирования нормализации орбит.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Проверка правил нормализации для парковки звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Проверка развертывания для остановки звонка</p></td>
<td><p>Проверьте парковку и извлечение вызовов, чтобы убедиться в том, что конфигурация работает корректно.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Необязательно Проверка развертывания парковки звонков в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

