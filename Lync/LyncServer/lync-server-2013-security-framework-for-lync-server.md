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
ms.openlocfilehash: f84b7eaf3476624479d1ecb7c7bb564a4eae8ad9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510446"
---
# <a name="security-framework-for-lync-server-2013"></a>Инфраструктура безопасности для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-08_

В этом разделе представлен обзор основных элементов, которые формируют платформу безопасности для Microsoft Lync Server 2013. Понимание принципов совместной работы этих элементов важно для принятия обоснованных решений по обеспечению безопасности отдельного развертывания Lync Server 2013.

Это следующие элементы:

  - Доменные службы Active Directory (AD DS) предоставляют один надежный внутренний репозиторий для учетных записей пользователей и сетевых ресурсов.

  - Role-Based управления доступом (RBAC) позволяет делегировать административные задачи, сохраняя при этом высокие стандарты безопасности.

  - Инфраструктура открытых ключей (PKI) использует сертификаты, выданные доверенными центрами сертификации (CA), для проверки подлинности серверов и обеспечения целостности данных.

  - Протокол TLS, HTTPS over SSL (HTTPS) и взаимное TLS (MTLS) обеспечивают проверку подлинности конечных точек и шифрование IM. Потоки передачи аудио-и видеоданных и общего доступа к приложениям шифруются с помощью протокола Secure Real-Time Transport Protocol (SRTP).

  - Стандартизированные протоколы для проверки подлинности пользователей, где это возможно.

  - Windows PowerShell предоставляет функции безопасности, которые включены по умолчанию, чтобы пользователи не могли легко или непреднамеренно запускать сценарии.

Эти фундаментальные элементы безопасности используются вместе для определения доверенных пользователей, серверов, подключений и операций, которые помогут обеспечить надежную основу для Lync Server 2013.

<div>

## <a name="in-this-section"></a>Содержание

В подразделах этого раздела описывается, как каждый из этих фундаментальных элементов работает для повышения безопасности инфраструктуры Lync Server.

  - [Доменные службы Active Directory для Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Управление доступом на основе ролей (RBAC) для Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Инфраструктура открытого ключа для Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS и MTLS для Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Шифрование для Lync Server 2013](lync-server-2013-encryption.md)

  - [Проверка подлинности пользователей и клиентов для Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Средства управления Windows PowerShell и Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

