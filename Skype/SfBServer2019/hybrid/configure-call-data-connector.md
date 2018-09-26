---
title: Настройка подключения к данным звонка
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по настройке вызова подключения к данным, что позволяет телеметрии из Скайп for Business локально, чтобы просмотреть с помощью Скайп для бизнеса в Интернет средства.
ms.openlocfilehash: 38e74e76e09d03036419f16807841a67fdf3433a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030576"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="9281f-103">Настройка подключения к данным звонка</span><span class="sxs-lookup"><span data-stu-id="9281f-103">Configure Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

<span data-ttu-id="9281f-104">В этой статье описывается настройка вызова подключения к данным — один набор инструментов, который позволяет просматривать Скайп для бизнес-Server вызов качества данных с помощью Скайп средства Business Online вызов качества панели мониторинга (CQD) и вызвать аналитики (ЦС).</span><span class="sxs-lookup"><span data-stu-id="9281f-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="9281f-105">В выпуске ознакомительной версии доступна только вызова Analytics панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9281f-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="9281f-106">Дополнительные сведения о преимуществах вызова подключения к данным и необходимые условия, например требования к роли и настройке гибридного подключения можно [Планирование вызова подключения к данным](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9281f-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="9281f-107">Разрешить мониторинг</span><span class="sxs-lookup"><span data-stu-id="9281f-107">Enable Monitoring</span></span> 

<span data-ttu-id="9281f-108">Необходимо настроить вызовов данных (CDR) и сбора данных качества взаимодействия (QoE); в противном случае вызова аналитики и панелей мониторинга качества звонков не получение сведений для отображения.</span><span class="sxs-lookup"><span data-stu-id="9281f-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection; otherwise, the Call Analytics and Call Quality Dashboards won’t get information to display.</span></span> <span data-ttu-id="9281f-109">Перед вам настроить вызова средство подключения к данным, выполните действия, указанные в [Развертывание мониторинга в Скайп для Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) для настройки регистрации Вызовов и качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9281f-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE.</span></span>


## <a name="enable-call-data-connector"></a><span data-ttu-id="9281f-110">Разрешить подключения к данным звонка</span><span class="sxs-lookup"><span data-stu-id="9281f-110">Enable Call Data Connector</span></span>

<span data-ttu-id="9281f-111">Чтобы настроить и включить вызова подключения к данным, будут использовать следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="9281f-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="9281f-112">Командлет</span><span class="sxs-lookup"><span data-stu-id="9281f-112">Cmdlet</span></span>| <span data-ttu-id="9281f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9281f-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="9281f-114">Новый CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="9281f-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="9281f-115">Online командлет, который устанавливает сборщик данных через Интернет.</span><span class="sxs-lookup"><span data-stu-id="9281f-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="9281f-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="9281f-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="9281f-117">Online командлет, который извлекает сбора данных через Интернет.</span><span class="sxs-lookup"><span data-stu-id="9281f-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="9281f-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="9281f-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="9281f-119">Локальный командлет, который получает сведения о подключении, созданных с помощью командлета New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="9281f-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="9281f-120">SET-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="9281f-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="9281f-121">Локальный командлет, который сохраняет его в локальной копии сведения о подключении, созданных с помощью командлета New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="9281f-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="9281f-122">SET-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="9281f-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="9281f-123">Локальный командлет, который позволяет включить или отключить соединителя и настройка уровня области.</span><span class="sxs-lookup"><span data-stu-id="9281f-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="9281f-124">Настройка среды</span><span class="sxs-lookup"><span data-stu-id="9281f-124">Configure your environment</span></span> 

<span data-ttu-id="9281f-125">Для настройки среды для разрешения сборщик данных через Интернет, необходимо сначала войти к Скайп для бизнеса Online PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="9281f-125">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="9281f-126">Дополнительные сведения можно [Управлять Скайп для бизнеса в Интернет с помощью Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="9281f-126">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="9281f-127">Существует два метода для входа систему Скайп для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9281f-127">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="9281f-128">Из Скайп оболочки управления Business Server 2019 (рекомендуется метод)</span><span class="sxs-lookup"><span data-stu-id="9281f-128">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="9281f-129">Из другого сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="9281f-129">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="9281f-130">Выполните вход Скайп для бизнеса Online PowerShell из Скайп оболочки управления Business Server (рекомендуется метод)</span><span class="sxs-lookup"><span data-stu-id="9281f-130">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="9281f-131">Если включение соединитель в первый раз, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9281f-131">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="9281f-132">Если ошибка, которая подключение уже существует, это означает, что подключение данных вызов уже существует для клиента.</span><span class="sxs-lookup"><span data-stu-id="9281f-132">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="9281f-133">В этом случае выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9281f-133">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="9281f-134">Выполните вход Скайп для бизнеса Online PowerShell из другого сеанса PowerShell (необязательный метод)</span><span class="sxs-lookup"><span data-stu-id="9281f-134">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="9281f-135">Если включение соединитель в первый раз, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9281f-135">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="9281f-136">Если ошибка, которая подключение уже существует, это означает, что подключение данных вызов уже существует для клиента.</span><span class="sxs-lookup"><span data-stu-id="9281f-136">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="9281f-137">В этом случае выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9281f-137">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="9281f-138">Выходные данные приведенные выше команды содержит значение маркера, который требуется при настройке в локальную среду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9281f-138">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="9281f-139">Из внутри Скайп оболочки управления Business Server, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9281f-139">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="9281f-140">Настройка области</span><span class="sxs-lookup"><span data-stu-id="9281f-140">Configure the scope</span></span>

<span data-ttu-id="9281f-141">Вызов подключения к данным можно включить для конкретного сайта или для вашей всей Скайп для развертывания Business Server с помощью командлета Set-CsCloudCallDataConnectorConfiguration в Скайп оболочки управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9281f-141">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="9281f-142">Например следующая команда включает вызова подключения к данным на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="9281f-142">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="9281f-143">В дополнение к глобальные параметры параметры конфигурации вызова подключения к данным может быть назначен на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9281f-143">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="9281f-144">Это обеспечивает гибкость дополнительное управление, когда речь идет о мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9281f-144">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="9281f-145">К примеру администратор может включить переадресацию звонков подключения к данным для сайта Redmond, но отключить переадресацию звонков подключения к данным для сайта Дублин, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9281f-145">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="9281f-146">Параметры, настроенные в области узла, имеют более высокий приоритет, чем параметры, настроенные в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="9281f-146">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="9281f-147">Предположим, например, переадресации звонков подключения к данным включено в глобальной области, но этот параметр отключен на уровне сайта (для сайта Redmond).</span><span class="sxs-lookup"><span data-stu-id="9281f-147">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="9281f-148">Это означает, что вызов регистрации и сведения о качестве взаимодействия не будет необходимо перенаправлять пользователей на сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="9281f-148">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="9281f-149">Тем не менее пользователи в другие веб-сайты (то есть пользователи, управляемые в глобальных параметрах вместо параметры сайта Redmond) будут иметь их регистрации вызовов и пересылку сведений о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9281f-149">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="9281f-150">В следующей таблице показаны значения для наиболее часто используемые параметры, используемые вызова подключения к данным:</span><span class="sxs-lookup"><span data-stu-id="9281f-150">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  
|<span data-ttu-id="9281f-151">Свойство</span><span class="sxs-lookup"><span data-stu-id="9281f-151">Property</span></span>|<span data-ttu-id="9281f-152">Описание</span><span class="sxs-lookup"><span data-stu-id="9281f-152">Description</span></span>|<span data-ttu-id="9281f-153">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9281f-153">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9281f-154">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="9281f-154">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="9281f-155">Указывает, включена ли вызов подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="9281f-155">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="9281f-156">Если значение True, мониторинг записей будет перенаправляться online мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9281f-156">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="9281f-157">$False</span><span class="sxs-lookup"><span data-stu-id="9281f-157">$False</span></span>  <br/> |
| <span data-ttu-id="9281f-158">Identity </span><span class="sxs-lookup"><span data-stu-id="9281f-158">Identity</span></span> | <span data-ttu-id="9281f-159">Определяет уровень области командой: глобальные или сайта.</span><span class="sxs-lookup"><span data-stu-id="9281f-159">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="9281f-160">глобальные</span><span class="sxs-lookup"><span data-stu-id="9281f-160">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="9281f-161">Отключение вызова подключения к данным</span><span class="sxs-lookup"><span data-stu-id="9281f-161">Disable Call Data Connector</span></span>

<span data-ttu-id="9281f-162">Отключение вызова подключения к данным разорвать связь хранилищу данных наблюдения из пула переднего плана, а также его удаления или повлиять на во внутренней базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9281f-162">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="9281f-163">При отключении вызова подключения к данным, остановите Скайп для Business Server из передача данных вызовов в облаке.</span><span class="sxs-lookup"><span data-stu-id="9281f-163">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="9281f-164">Отключение вызова подключения к данным с помощью командлета Set-CsCloudCallDataConnectorConfiguration в Скайп оболочки управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9281f-164">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="9281f-165">К примеру следующая команда выключает вызова подключения к данным на глобальном уровне путем установки свойства EnableCallDataConnector значение $False.</span><span class="sxs-lookup"><span data-stu-id="9281f-165">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="9281f-166">Если нужно восстановить, передача данных вызовов в облаке, необходимо задайте свойство EnableCallDataConnector обратно значение $True, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9281f-166">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="9281f-167">Просмотр локальных данных через Интернет панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="9281f-167">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="9281f-168">После включения вызова подключения к данным можно просмотреть данные вызова в локальной на панели мониторинга вызова аналитики, как описано в [Аналитике вызова используется для устранения неполадок плохого качества](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="9281f-168">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="9281f-169">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9281f-169">For more information</span></span>

<span data-ttu-id="9281f-170">Дополнительные сведения о командлеты можно использовать команду Get-Help из Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="9281f-170">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9281f-171">Например:</span><span class="sxs-lookup"><span data-stu-id="9281f-171">For example:</span></span>
  
<span data-ttu-id="9281f-172">Get-Help Get-CsCloudCallDataConnector | Дополнительные</span><span class="sxs-lookup"><span data-stu-id="9281f-172">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="9281f-173">Get-Help Set-CsCloudCallDataConnector | Дополнительные</span><span class="sxs-lookup"><span data-stu-id="9281f-173">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="9281f-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | Дополнительные</span><span class="sxs-lookup"><span data-stu-id="9281f-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>