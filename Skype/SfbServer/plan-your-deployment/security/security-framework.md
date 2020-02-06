---
title: Платформа безопасности для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: В этом разделе приводятся общие сведения об основных элементах, которые формируют структуру безопасности для Skype для бизнеса Server. Понимание того, как эти элементы работают вместе, очень важно для принятия обоснованных решений по обеспечению безопасности конкретного развертывания Skype для бизнеса Server.
ms.openlocfilehash: 432d4cda013e5bdec2613e3c9052f10b7d619302
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815617"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="eb8d4-104">Платформа безопасности для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="eb8d4-105">В этом разделе приводятся общие сведения об основных элементах, которые формируют структуру безопасности для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="eb8d4-106">Понимание того, как эти элементы работают вместе, очень важно для принятия обоснованных решений по обеспечению безопасности конкретного развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="eb8d4-107">Ниже представлены эти элементы.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="eb8d4-108">Доменные службы Active Directory (AD DS) предоставляют единый доверенный серверный репозиторий для учетных записей пользователей и сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="eb8d4-109">Управление доступом на основе ролей (RBAC) позволяет делегировать административные задачи, обеспечивая при этом поддержку высоких стандартов безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="eb8d4-110">Инфраструктура открытых ключей (PKI) использует сертификаты, выданные доверенными центрами сертификации (ЦС) с целью проверки подлинности серверов и обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="eb8d4-p103">Безопасность на транспортном уровне (TLS), передача HTTPS по SSL (HTTPS) и взаимные подключения по протоколу TLS (MTLS) позволяют выполнять проверку подлинности конечной точки и шифровать обмен мгновенными сообщениями. Потоки информации одноранговых сеансов обмена аудио- и видеоданными и общего доступа к приложениям шифруются с использованием протокола SRTP.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="eb8d4-113">Протоколы отраслевых стандартов для проверки подлинности пользователя (по мере возможности).</span><span class="sxs-lookup"><span data-stu-id="eb8d4-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="eb8d4-114">Windows PowerShell предоставляет функции безопасности, которые включены по умолчанию, чтобы пользователи не могли легко или непреднамеренно запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="eb8d4-115">Эти фундаментальные элементы безопасности вместе служат для определения доверенных пользователей, серверов, подключений и операций, чтобы обеспечить надежную основу для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="eb8d4-116">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="eb8d4-116">In this section</span></span>

<span data-ttu-id="eb8d4-117">В этой статье описывается, как все эти фундаментальные элементы помогают повысить безопасность инфраструктуры сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="eb8d4-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="eb8d4-118">Доменные службы Active Directory для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="eb8d4-119">Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="eb8d4-120">Инфраструктура открытых ключей для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="eb8d4-121">TLS и MTLS для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="eb8d4-122">Шифрование для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="eb8d4-123">Проверка подлинности пользователей и клиентов для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="eb8d4-124">Средства управления Windows PowerShell и Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb8d4-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

