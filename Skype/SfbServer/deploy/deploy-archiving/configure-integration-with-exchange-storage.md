---
title: Настройка интеграции с хранилищем Exchange для Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как настроить интеграцию с хранилищем Exchange в Скайп для Business Server.'
ms.openlocfilehash: 5f987ef0c2c47960a71c94a3b5a692062e787ed6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988334"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="a641b-103">Настройка интеграции с хранилищем Exchange для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="a641b-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="a641b-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как настроить интеграцию с хранилищем Exchange в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="a641b-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="a641b-105">При использовании интеграции с Microsoft Exchange для всех пользователей в вашем развертывании не нужно настроить Скайп для Business Server политик архивации для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a641b-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="a641b-106">Вместо этого настройте политики хранения на месте Exchange для поддержки архивации для пользователей, размещенных на сервере Exchange, с их почтовых ящиков, поставленных на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="a641b-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a641b-107">Перед настройкой интеграции с хранилищем Exchange чтение [Планирование архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a641b-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="a641b-108">Для получения дополнительных сведений о политиках хранения на месте Exchange обратитесь к документации Exchange.</span><span class="sxs-lookup"><span data-stu-id="a641b-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="a641b-109">Настройка интеграции с хранилищем Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="a641b-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="a641b-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a641b-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a641b-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="a641b-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a641b-112">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="a641b-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="a641b-113">В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a641b-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
  - <span data-ttu-id="a641b-114">Чтобы включить интеграцию с хранилищем Exchange, установите флажок **Интеграция с Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a641b-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
  - <span data-ttu-id="a641b-115">Чтобы отключить интеграцию с хранилищем Exchange, снимите флажок **Интеграция с Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a641b-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="a641b-116">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a641b-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="a641b-117">При развертывании Скайп Business Server и Microsoft Exchange в разных лесах</span><span class="sxs-lookup"><span data-stu-id="a641b-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="a641b-118">При использовании интеграции с Microsoft Exchange и Microsoft Exchange Server не развертываются в том же лесу, что Скайп для Business Server, необходимо убедиться, что следующие атрибуты Active Directory в Exchange синхронизируется в лес где Скайп для Развертывается Business Server:</span><span class="sxs-lookup"><span data-stu-id="a641b-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="a641b-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a641b-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="a641b-120">proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="a641b-120">proxyAddresses</span></span>
    
<span data-ttu-id="a641b-p102">Это атрибут со множеством значений. При его синхронизации необходимо объединить значения, а не заменить их, чтобы текущие значения не были потеряны.</span><span class="sxs-lookup"><span data-stu-id="a641b-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

