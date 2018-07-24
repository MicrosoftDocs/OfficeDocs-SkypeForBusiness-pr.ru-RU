---
title: Модель безопасности для Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: В этом разделе приведен обзор основных элементов, формирующих модель безопасности для Скайп для Business Server. Общие сведения о совместной работе этих элементов необходимо для принятия обоснованных решений о защите вашей конкретной Скайп для развертывания Business Server.
ms.openlocfilehash: 487b3ea7f57c1a008327be2b9b31664a160e8425
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983618"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="e985f-104">Модель безопасности для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e985f-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="e985f-105">В этом разделе приведен обзор основных элементов, формирующих модель безопасности для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="e985f-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="e985f-106">Общие сведения о совместной работе этих элементов необходимо для принятия обоснованных решений о защите вашей конкретной Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="e985f-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="e985f-107">Ниже представлены эти элементы.</span><span class="sxs-lookup"><span data-stu-id="e985f-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="e985f-108">Доменных служб Active Directory (AD DS) предоставляет одного надежного серверной хранилище учетных записей пользователей и сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e985f-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="e985f-109">Управление доступом на основе ролей (RBAC) позволяет делегировать административные задачи, обеспечивая при этом поддержку высоких стандартов безопасности.</span><span class="sxs-lookup"><span data-stu-id="e985f-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="e985f-110">Инфраструктура открытых ключей (PKI) использует сертификаты, выданные доверенными центрами сертификации (ЦС) с целью проверки подлинности серверов и обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="e985f-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="e985f-p103">Безопасность на транспортном уровне (TLS), передача HTTPS по SSL (HTTPS) и взаимные подключения по протоколу TLS (MTLS) позволяют выполнять проверку подлинности конечной точки и шифровать обмен мгновенными сообщениями. Потоки информации одноранговых сеансов обмена аудио- и видеоданными и общего доступа к приложениям шифруются с использованием протокола SRTP.</span><span class="sxs-lookup"><span data-stu-id="e985f-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="e985f-113">Протоколы отраслевых стандартов для проверки подлинности пользователя (по мере возможности).</span><span class="sxs-lookup"><span data-stu-id="e985f-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="e985f-114">Windows PowerShell предоставляет функции безопасности, для которых включено по умолчанию, чтобы пользователи не могут легко или непреднамеренно выполнение скриптов.</span><span class="sxs-lookup"><span data-stu-id="e985f-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="e985f-115">Эти элементы системы безопасности фундаментальные работают вместе для определения надежным пользователям, серверы, подключений и операций для обеспечения безопасной foundation для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="e985f-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e985f-116">Содержание</span><span class="sxs-lookup"><span data-stu-id="e985f-116">In this section</span></span>

<span data-ttu-id="e985f-117">В этом разделе описываются принципы работы каждого из этих основных элементов для повышения безопасности вашей Скайп для инфраструктуры Business Server.</span><span class="sxs-lookup"><span data-stu-id="e985f-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="e985f-118">Доменные службы Active Directory для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e985f-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="e985f-119">Управление доступом на основе ролей (RBAC) для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e985f-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="e985f-120">Инфраструктура открытого ключа для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e985f-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="e985f-121">Протокол TLS и MTLS для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e985f-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="e985f-122">Шифрование для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e985f-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="e985f-123">Пользователь и клиент проверки подлинности Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e985f-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="e985f-124">Скайп для средств управления Business Server и Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e985f-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

