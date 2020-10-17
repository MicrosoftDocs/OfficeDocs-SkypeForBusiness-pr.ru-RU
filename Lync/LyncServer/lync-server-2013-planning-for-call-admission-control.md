---
title: 'Lync Server 2013: Планирование контроля допуска звонков'
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
ms.openlocfilehash: a7c101ab49d16b01dd35d4fc498f002747cd31cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497816"
---
# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Планирование контроля допуска звонков в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Для приложений Объединенных коммуникаций (UC), использующих протокол IP, таких как телефония, видео и общий доступ к приложениям, доступная пропускная способность корпоративных сетей, как правило, не считается ограничивающим фактором в средах ЛВС. Однако в каналах глобальной сети, соединяющих сайты, пропускная способность сети может быть ограничена. Когда наплыва сетевого трафика записывает связь WAN, для устранения перегрузки используются текущие механизмы, такие как очередь, буферизация и удаление пакетов. Дополнительный трафик обычно задерживается до тех пор, пока перегрузка сети не задерживается или при необходимости отклоняется трафик. Для обычного трафика данных в таких ситуациях принимающий клиент может выполнить восстановление. Для трафика в режиме реального времени, например единой системы обмена сообщениями, перегрузка сети не может быть разрешена таким образом, так как трафик единой системы обмена сообщениями зависит как от задержки, так и от потери пакетов. Перегрузка WAN может привести к неудовлетворительному качеству работы (QoE) для пользователей. Для трафика в режиме реального времени в перегруженных условиях лучше отклонять вызовы, а не предоставлять подключения с низким качеством.

Контроль допуска звонков (CAC) определяет, достаточно ли пропускной способности сети для установления сеанса в режиме реального времени. В Lync Server 2013 CAC управляет трафиком в режиме реального времени только для аудио и видео, но не влияет на трафик данных. Если канал глобальной сети по умолчанию не имеет необходимой пропускной способности, CAC может попытаться маршрутизировать вызов через Интернет или телефонную сеть общего пользования (PSTN). CAC можно использовать только в Lync Server.

В этом разделе описываются функции контроля допуска звонков и описано, как спланировать CAC.

<div>


> [!NOTE]  
> Lync Server включает три расширенные функции корпоративной голосовой связи: контроль допуска звонков (CAC), экстренные службы (E9-1-1) и обход сервера-посредника. Общие сведения о планировании, которые являются общими для всех трех этих функций, приведены в разделе <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Параметры сети для расширенных функций корпоративной голосовой связи в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Обзор контроля допуска звонков в Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Определение требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Компоненты и топологии для CAC в Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Рекомендации по контролю допуска звонков в Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Контрольный список развертывания для контроля допуска звонков в Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

