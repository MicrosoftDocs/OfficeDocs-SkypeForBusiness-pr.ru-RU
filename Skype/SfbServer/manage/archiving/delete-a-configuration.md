---
title: Удаление конфигурации архивации в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Сводка: Узнайте, как удалить конфигурации архивации в Скайп для Business Server.'
ms.openlocfilehash: 3b6f79247a03beae4abc917d38a6844d67324082
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884981"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="6b5a0-103">Удаление конфигурации архивации в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6b5a0-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="6b5a0-104">**Сводка:** Узнайте, как удалить конфигурации архивации в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="6b5a0-p101">Конфигурацию сайта или пула можно удалить, но удаление глобальной конфигурации невозможно. При удалении глобальной конфигурации она автоматически восстанавливает значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="6b5a0-107">Удаление конфигурации архивирования с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="6b5a0-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="6b5a0-108">Чтобы удалить конфигурацию архивирования с помощью панели управления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6b5a0-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="6b5a0-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="6b5a0-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6b5a0-111">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6b5a0-112">В списке конфигураций архивирования нажмите конфигурацию сайта или пула, которую необходимо удалить, затем выберите **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6b5a0-113">Также можно выбрать глобальную конфигурацию, но это следует делать только в том случае, если вы хотите сбросить глобальную конфигурацию к параметрам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="6b5a0-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="6b5a0-115">Удаление конфигурации архивирования с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b5a0-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="6b5a0-116">Также можно удалить конфигурации архивации с помощью командлета **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6b5a0-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="6b5a0-p102">Например, следующая команда удаляет параметры конфигурации архивирования, которые применены к сайту Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="6b5a0-119">Следующая команда удаляет все параметры конфигурации архивирования, применяемые на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="6b5a0-120">Эта команда удаляет все параметры конфигурации архивирования, в которых отключена служба архивации Exchange.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="6b5a0-121">Для сброса глобальных параметров до значений по умолчанию можно также использовать командлет **Remove-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6b5a0-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="6b5a0-122">Например, предположим, что на глобальном уровне включена архивация сеанса обмена мгновенными сообщениями; следующая команда выполнит сброс значений до значения по умолчанию "Нет", что приведет к отключению архивации на глобальном уровне:</span><span class="sxs-lookup"><span data-stu-id="6b5a0-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="6b5a0-123">Для получения дополнительных сведений см раздел справки для командлета [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="6b5a0-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
