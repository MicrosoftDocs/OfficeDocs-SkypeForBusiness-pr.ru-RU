---
title: 'Lync Server 2013: планирование контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Планирование контроля допуска звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Для приложений Объединенных коммуникаций (UC), использующих протокол IP, таких как телефония, видео и общий доступ к приложениям, доступная пропускная способность сетей предприятий, как правило, не рассматривается как ограничивающий фактор в среде ЛВС. Однако на WAN-каналах, которые соединяют узлы, пропускная полоса сети может быть ограничена. Когда инфлукс сетевой трафик переписывается на ГЛОБАЛЬную ссылку, для устранения перегрузки используются текущие механизмы, такие как очередь, буферизация и сбрасывание пакетов. Дополнительный трафик, как правило, задерживается, пока перегрузка сети не будет устранена или, при необходимости, пока трафик не будет отброшен. Для обычного трафика данных в подобных ситуациях принимающий клиент может восстановиться. Для трафика в реальном времени, такого как единая связь, перегрузка сети не может быть разрешена таким образом, так как трафик единой системы обмена сообщениями чувствителен к задержке и потере пакетов. Перегрузка канала глобальной сети может привести к ухудшению качества взаимодействия (QoE) для пользователей. Для трафика в режиме реального времени в перегруженных условиях лучше запретить звонки, чем предоставлять соединения с низким качеством.

Контроль допуска звонков (CAC) определяет, достаточно ли пропускной полосы для установления сеанса связи допустимого качества в реальном времени. В Lync Server 2013 CAC управляет трафиком в реальном времени только для звуковых и видеофайлов, но не влияет на трафик данных. Если у WAN-канала по умолчанию нет необходимой пропускной полосы, CAC может попытаться направить вызов через Интернет или телефонную сеть общего пользования (ТСОП). CAC поддерживается только в Lync Server.

В этом разделе приведено описание функций контроля допуска звонков и планирование использования CAC.

<div>


> [!NOTE]  
> На сервере Lync Server есть три опытных услуги голосовой связи: управление допуском звонков (CAC), службы экстренной помощи (E9-1) и обход мультимедиа. Общие сведения о планировании, которые являются общими для всех трех из этих функций, приведены в разделе <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Параметры сети для опытных функций корпоративного голосовой связи в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Общие сведения об управлении допуском звонков в Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Определение своих требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Пример: сбор требований к управлению допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Компоненты и топологии для контроля допуска звонков в Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Рекомендации по контролю допуска звонков в Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Контрольный список развертывания для контроля допуска звонков в Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

