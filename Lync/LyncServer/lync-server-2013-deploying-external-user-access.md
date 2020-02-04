---
title: 'Lync Server 2013: развертывание доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba083650b9a068d48e28bf8af0c51b4b25b5c227
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a>Развертывание доступа внешних пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-09-23_

Развертывание компонентов Edge для Microsoft Lync Server 2013 делает возможным для внешних пользователей, которые не вошли в внутреннюю сеть Организации, включая пользователей, прошедших проверку подлинности и анонимные удаленные пользователи, Федеративные партнеры (в том числе партнеры КСМПП). мобильные клиенты и пользователи общедоступных служб обмена мгновенными сообщениями (IM) для общения с другими пользователями в Организации с помощью Lync Server. Процессы развертывания и конфигурации для Lync Server 2013 значительно отличаются от Lync Server 2010. Средства для установки и администрирования в Lync Server 2010 очень одинаковы.

<div>


> [!IMPORTANT]  
> Установка и Настройка пограничного сервера Microsoft Lync Server 2013&nbsp;может быть сложной задачей, требующей потенциальной значительной процедуры планирования и координации с внутренними группами, включая (но не ограничиваясь ограничениями) системы безопасности, сети, брандмауэра, системы доменных имен (DNS), подсистему балансировки нагрузки и инфраструктуры открытых ключей (PKI). Прежде чем развертывать компоненты внешнего доступа, настоятельно рекомендуется просмотреть и использовать процесс планирования и документацию, описанные выше. Это поможет вам ограничить количество и частоту нежелательных изменений и проблем, как только вы пройдете в процессе развертывания. Сведения о планировании внешнего доступа пользователей можно найти <A href="lync-server-2013-planning-for-external-user-access.md">в разделе Планирование доступа внешних пользователей в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Контрольный список развертывания для доступа внешних пользователей в Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [Системные требования для компонентов доступа внешних пользователей для Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Подготовка к установке серверов в сети периметра для Lync Server 2013](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [Создание топологии пограничных серверов и директора в Lync Server 2013](lync-server-2013-building-an-edge-and-director-topology.md)

  - [Настройка режиссера в Lync Server 2013](lync-server-2013-setting-up-the-director.md) (необязательно)

  - [Настройка пограничных серверов в Lync Server 2013](lync-server-2013-setting-up-edge-servers.md)

  - [Настройка обратных прокси-серверов для Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [Настройка поддержки доступа внешних пользователей в Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Руководство по подготовке взаимодействия Lync-Skype в Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [Настройка федерации SIP, федерации XMPP и общедоступных служб обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [Развертывание поддержки мобильной работы в Lync Server 2013](lync-server-2013-deploying-mobility.md)

  - [Проверка развертывания пограничного сервера в Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

