---
title: 'Lync Server 2013: инфраструктура безопасности для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a2b58d34c1ed1f899e0daac8c1bb0132b1a22d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Платформа безопасности для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-08_

В этом разделе приводятся общие сведения об основных элементах, которые формируют структуру безопасности для Microsoft Lync Server 2013. Понимание того, как эти элементы работают вместе, очень важно для принятия обоснованных решений по обеспечению безопасности конкретного развертывания Lync Server 2013.

Ниже представлены эти элементы.

  - Доменные службы Active Directory (AD DS) предоставляют единый доверенный серверный репозиторий для учетных записей пользователей и сетевых ресурсов.

  - Управление доступом на основе ролей (RBAC) позволяет делегировать административные задачи, обеспечивая при этом поддержку высоких стандартов безопасности.

  - Инфраструктура открытых ключей (PKI) использует сертификаты, выданные доверенными центрами сертификации (ЦС) с целью проверки подлинности серверов и обеспечения целостности данных.

  - Безопасность на транспортном уровне (TLS), передача HTTPS по SSL (HTTPS) и взаимные подключения по протоколу TLS (MTLS) позволяют выполнять проверку подлинности конечной точки и шифровать обмен мгновенными сообщениями. Потоки информации одноранговых сеансов обмена аудио- и видеоданными и общего доступа к приложениям шифруются с использованием протокола SRTP.

  - Протоколы отраслевых стандартов для проверки подлинности пользователя (по мере возможности).

  - Windows PowerShell предоставляет функции безопасности, которые включены по умолчанию, чтобы пользователи не могли легко или непреднамеренно запускать сценарии.

Эти фундаментальные элементы безопасности вместе используются для определения доверенных пользователей, серверов, подключений и операций, чтобы обеспечить надежную основу для Lync Server 2013.

<div>

## <a name="in-this-section"></a>Содержание

В этом разделе объясняется, как все эти фундаментальные элементы помогают повысить безопасность инфраструктуры Lync Server.

  - [Доменные службы Active Directory для Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Управление доступом на основе ролей (RBAC) для Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Инфраструктура открытых ключей для Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS и MTLS для Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Шифрование для Lync Server 2013](lync-server-2013-encryption.md)

  - [Проверка подлинности пользователей и клиентов для Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Средства управления для Windows PowerShell и Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

