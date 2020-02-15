---
title: Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fc69514b425c6a619a0edcd349a8b8733eca369
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a>Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-10_

Политики голосовой связи, записи использования ТСОП и маршруты голосовых вызовов тесно связаны. Вы настраиваете политики голосовой связи, выбирая набор возможностей звонков и назначая политике набор записей использования ТСОП, указывающих, какие права разрешены для пользователей или групп, которым назначена политика голосовой связи. Маршрутам голосовых вызовов также назначаются записи использования ТСОП, служащие для сопоставления маршрутов с пользователями, которым разрешено эти маршруты использовать. Таким образом, пользователи могут выполнять только звонки, использующие маршруты, для которых имеется соответствующая запись использования ТСОП.

Рекомендуемый рабочий процесс для нового развертывания корпоративной голосовой связи заключается в том, чтобы начать с настройки политики голосовой связи, включающей в себя подходящие записи использования ТСОП, а затем сопоставить соответствующие маршруты с каждой из записей использования ТСОП.

<div>


> [!NOTE]
> Вы также можете создать политики голосовой связи с использованием области <EM>пользователей</EM> и назначить их отдельным пользователям или группам.



</div>

Подробные сведения о выполнении каждой из этих задач см. процедуры, приведенные в данном разделе.

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка политики голосовой связи и записей использования PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Просмотр записей использования PSTN в Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)

  - [Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Экспорт и импорт конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Проверка маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

