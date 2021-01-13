---
title: Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: Сводка. В этом разделе вы узнаете, как настроить интеграцию с хранилищем Exchange в Skype для бизнеса Server.
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825069"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="64e11-103">Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="64e11-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="64e11-104">**Сводка:** В этом разделе вы узнаете, как настроить интеграцию с хранилищем Exchange в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="64e11-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="64e11-105">Если вы используете интеграцию Microsoft Exchange для всех пользователей в развертывании, вам не нужно настраивать политики архивации Skype для бизнеса Server для пользователей.</span><span class="sxs-lookup"><span data-stu-id="64e11-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="64e11-106">Вместо этого политики удержания In-Place Exchange настраиваются для поддержки архива для пользователей, которые были In-Place exchange.</span><span class="sxs-lookup"><span data-stu-id="64e11-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="64e11-107">Перед настройкой интеграции с хранилищем Exchange ознакомьтесь с планом архивации [в Skype для бизнеса Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="64e11-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="64e11-108">Подробные сведения о политиках In-Place Exchange см. в документации по продуктам Exchange.</span><span class="sxs-lookup"><span data-stu-id="64e11-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="64e11-109">Настройка интеграции с хранилищем Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="64e11-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="64e11-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="64e11-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64e11-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="64e11-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="64e11-112">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="64e11-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="64e11-113">Щелкните имя соответствующей конфигурации — глобальной, сайта или пула — в списке конфигураций архивирования, затем щелкните **Правка**, щелкните **Показать подробности** и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="64e11-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="64e11-114">Чтобы включить интеграцию с хранилищем Exchange, выберите **этот** окне.</span><span class="sxs-lookup"><span data-stu-id="64e11-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="64e11-115">Чтобы отключить интеграцию с хранилищем Exchange, с помощью этого окне необходимо с **помощью** этого окна.</span><span class="sxs-lookup"><span data-stu-id="64e11-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="64e11-116">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="64e11-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="64e11-117">Развертывание Skype для бизнеса Server и Microsoft Exchange в разных лесах</span><span class="sxs-lookup"><span data-stu-id="64e11-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="64e11-118">Если вы используете интеграцию Microsoft Exchange и Microsoft Exchange Server развернуты не в том же лесу, что и Skype для бизнеса Server, необходимо убедиться, что следующие атрибуты Exchange Active Directory синхронизированы с лесом, в котором развернут Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="64e11-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="64e11-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="64e11-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="64e11-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="64e11-120">proxyAddresses</span></span>
    
<span data-ttu-id="64e11-p102">Это атрибут со множеством значений. При его синхронизации необходимо объединить значения, а не заменить их, чтобы текущие значения не были потеряны.</span><span class="sxs-lookup"><span data-stu-id="64e11-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

