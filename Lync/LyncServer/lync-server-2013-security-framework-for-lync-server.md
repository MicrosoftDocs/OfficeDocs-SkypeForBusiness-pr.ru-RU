---
title: 'Lync Server 2013: инфраструктура безопасности для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="300db-102">Платформа безопасности для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="300db-103">_**Тема последнего изменения:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="300db-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="300db-104">В этом разделе приводятся общие сведения об основных элементах, которые формируют структуру безопасности для Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="300db-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="300db-105">Понимание того, как эти элементы работают вместе, очень важно для принятия обоснованных решений по обеспечению безопасности конкретного развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="300db-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="300db-106">Ниже представлены эти элементы.</span><span class="sxs-lookup"><span data-stu-id="300db-106">These elements are as follows:</span></span>

  - <span data-ttu-id="300db-107">Доменные службы Active Directory (AD DS) предоставляют единый доверенный серверный репозиторий для учетных записей пользователей и сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="300db-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="300db-108">Управление доступом на основе ролей (RBAC) позволяет делегировать административные задачи, обеспечивая при этом поддержку высоких стандартов безопасности.</span><span class="sxs-lookup"><span data-stu-id="300db-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="300db-109">Инфраструктура открытых ключей (PKI) использует сертификаты, выданные доверенными центрами сертификации (ЦС) с целью проверки подлинности серверов и обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="300db-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="300db-p102">Безопасность на транспортном уровне (TLS), передача HTTPS по SSL (HTTPS) и взаимные подключения по протоколу TLS (MTLS) позволяют выполнять проверку подлинности конечной точки и шифровать обмен мгновенными сообщениями. Потоки информации одноранговых сеансов обмена аудио- и видеоданными и общего доступа к приложениям шифруются с использованием протокола SRTP.</span><span class="sxs-lookup"><span data-stu-id="300db-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="300db-112">Протоколы отраслевых стандартов для проверки подлинности пользователя (по мере возможности).</span><span class="sxs-lookup"><span data-stu-id="300db-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="300db-113">Windows PowerShell предоставляет функции безопасности, которые включены по умолчанию, чтобы пользователи не могли легко или непреднамеренно запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="300db-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="300db-114">Эти фундаментальные элементы безопасности вместе используются для определения доверенных пользователей, серверов, подключений и операций, чтобы обеспечить надежную основу для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="300db-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="300db-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="300db-115">In This Section</span></span>

<span data-ttu-id="300db-116">В этом разделе объясняется, как все эти фундаментальные элементы помогают повысить безопасность инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="300db-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="300db-117">Доменные службы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="300db-118">Управление доступом на основе ролей (RBAC) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="300db-119">Инфраструктура открытых ключей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="300db-120">TLS и MTLS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="300db-121">Шифрование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="300db-122">Проверка подлинности пользователей и клиентов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="300db-123">Средства управления для Windows PowerShell и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="300db-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

