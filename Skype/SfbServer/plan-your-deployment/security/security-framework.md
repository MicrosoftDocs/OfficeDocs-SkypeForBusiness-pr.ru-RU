---
title: Структура безопасности для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: В этом разделе представлен обзор основных элементов, форм составляющих структуру безопасности skype для бизнеса Server. Понимание совместной работы этих элементов крайне важно для принятия обоснованных решений о защите конкретного развертывания Skype для бизнеса Server.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832099"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="884f9-104">Структура безопасности для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="884f9-105">В этом разделе представлен обзор основных элементов, форм составляющих структуру безопасности Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="884f9-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="884f9-106">Понимание совместной работы этих элементов крайне важно для принятия обоснованных решений о защите конкретного развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="884f9-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="884f9-107">Эти элементы следуют следующим образом:</span><span class="sxs-lookup"><span data-stu-id="884f9-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="884f9-108">Доменные службы Active Directory (AD DS) предоставляют единый надежный репозиторий для учетных записей пользователей и сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="884f9-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="884f9-109">Role-Based управления доступом (RBAC) позволяет делегировать административные задачи, сохраняя при этом высокие стандарты безопасности.</span><span class="sxs-lookup"><span data-stu-id="884f9-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="884f9-110">Инфраструктура открытых ключей (PKI) использует сертификаты, выданные доверенными центрами сертификации (ЦС), для проверки подлинности серверов и обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="884f9-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="884f9-111">Протокол TLS, протокол HTTPS через SSL (HTTPS) и протокол MTLS обеспечивают проверку подлинности конечной точки и шифрование мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="884f9-111">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="884f9-112">Потоки аудио- и видеосвязи и общего доступа к приложениям "точка-точка" шифруются с помощью протокола Real-Time Secure Real-Time Transport Protocol (SRTP).</span><span class="sxs-lookup"><span data-stu-id="884f9-112">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="884f9-113">Отраслевые протоколы для проверки подлинности пользователей, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="884f9-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="884f9-114">Windows PowerShell функции безопасности, которые включены по умолчанию, чтобы пользователи не могли легко или непреднастраиво запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="884f9-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="884f9-115">Эти основные элементы безопасности совместно определяют надежных пользователей, серверы, подключения и операции, чтобы обеспечить безопасную основу для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="884f9-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="884f9-116">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="884f9-116">In this section</span></span>

<span data-ttu-id="884f9-117">В этом разделе описывается, как каждый из этих основных элементов работает для повышения безопасности инфраструктуры Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="884f9-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="884f9-118">Доменные службы Active Directory для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="884f9-119">Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="884f9-120">Инфраструктура открытых ключей для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="884f9-121">TLS и MTLS для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="884f9-122">Шифрование для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="884f9-123">Проверка подлинности пользователей и клиентов для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="884f9-124">Windows PowerShell и средства управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="884f9-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

