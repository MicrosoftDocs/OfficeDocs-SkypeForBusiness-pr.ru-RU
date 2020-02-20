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
ms.openlocfilehash: 472e15d2206e787abb571885f0155bb0169f7234
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="740dd-102">Инфраструктура безопасности для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="740dd-103">_**Последнее изменение темы:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="740dd-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="740dd-104">В этом разделе представлен обзор основных элементов, которые формируют платформу безопасности для Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="740dd-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="740dd-105">Понимание принципов совместной работы этих элементов важно для принятия обоснованных решений по обеспечению безопасности отдельного развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="740dd-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="740dd-106">Это следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="740dd-106">These elements are as follows:</span></span>

  - <span data-ttu-id="740dd-107">Доменные службы Active Directory (AD DS) предоставляют один надежный внутренний репозиторий для учетных записей пользователей и сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="740dd-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="740dd-108">Управление доступом на основе ролей (RBAC) позволяет делегировать административные задачи, сохраняя при этом высокие стандарты безопасности.</span><span class="sxs-lookup"><span data-stu-id="740dd-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="740dd-109">Инфраструктура открытых ключей (PKI) использует сертификаты, выданные доверенными центрами сертификации (CA), для проверки подлинности серверов и обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="740dd-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="740dd-110">Протокол TLS, HTTPS over SSL (HTTPS) и взаимное TLS (MTLS) обеспечивают проверку подлинности конечных точек и шифрование IM.</span><span class="sxs-lookup"><span data-stu-id="740dd-110">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="740dd-111">Потоки обмена аудио-и видеоданных и общего доступа к приложениям шифруются с помощью протокола Secure SRTP.</span><span class="sxs-lookup"><span data-stu-id="740dd-111">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="740dd-112">Стандартизированные протоколы для проверки подлинности пользователей, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="740dd-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="740dd-113">Windows PowerShell предоставляет функции безопасности, которые включены по умолчанию, чтобы пользователи не могли легко или непреднамеренно запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="740dd-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="740dd-114">Эти фундаментальные элементы безопасности используются вместе для определения доверенных пользователей, серверов, подключений и операций, которые помогут обеспечить надежную основу для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="740dd-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="740dd-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="740dd-115">In This Section</span></span>

<span data-ttu-id="740dd-116">В подразделах этого раздела описывается, как каждый из этих фундаментальных элементов работает для повышения безопасности инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="740dd-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="740dd-117">Доменные службы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="740dd-118">Управление доступом на основе ролей (RBAC) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="740dd-119">Инфраструктура открытого ключа для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="740dd-120">TLS и MTLS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="740dd-121">Шифрование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="740dd-122">Проверка подлинности пользователей и клиентов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="740dd-123">Средства управления Windows PowerShell и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740dd-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

