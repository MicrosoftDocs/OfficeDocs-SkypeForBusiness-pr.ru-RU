---
title: Настройка соединителя данных звонка
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по настройке соединиттеля данных вызовов, который позволяет просматривать телеметрию из локального skype для бизнеса с помощью инструментов Skype для бизнеса Online.
ms.openlocfilehash: f78d59d02964bd826fc705bc193cae3e21b293a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118998"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="5a87f-103">Настройка соединителя данных звонка</span><span class="sxs-lookup"><span data-stu-id="5a87f-103">Configure Call Data Connector</span></span>

<span data-ttu-id="5a87f-104">В этой статье описывается настройка соединитетеля данных вызовов — единого средства, который позволяет просматривать качественные данные skype для бизнес-серверов с помощью инструментов мониторинга качества вызовов Skype для бизнеса в Интернете и аналитики вызовов (CA).</span><span class="sxs-lookup"><span data-stu-id="5a87f-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="5a87f-105">Дополнительные сведения о преимуществах и предварительных требованиях к соединителу данных вызовов, таких как требования к роли и настройке гибридного подключения, см. в руб. [Plan Call Data Connector.](plan-call-data-connector.md)</span><span class="sxs-lookup"><span data-stu-id="5a87f-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="5a87f-106">Включить мониторинг</span><span class="sxs-lookup"><span data-stu-id="5a87f-106">Enable Monitoring</span></span>
 
<span data-ttu-id="5a87f-107">Необходимо настроить сбор данных для записи данных вызовов (CDR) и Quality of Experience (QoE) в переднем окантовке мониторинга пула с локальными базами данных LCSCdr и QoEMetrics; в противном случае панели мониторинга качества вызовов и вызовов не будут работать с данными.</span><span class="sxs-lookup"><span data-stu-id="5a87f-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="5a87f-108">Перед настройкой соединители данных вызовов выполните действия, предусмотренные в развертывании мониторинга в Skype для бизнеса [Server,](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) чтобы настроить CDR и QoE, а также базовый мониторинг.</span><span class="sxs-lookup"><span data-stu-id="5a87f-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a87f-109">Соединители данных вызовов не будут работать, если мониторинг не включен в переднем пуле.</span><span class="sxs-lookup"><span data-stu-id="5a87f-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="5a87f-110">Включить соединители данные вызовов</span><span class="sxs-lookup"><span data-stu-id="5a87f-110">Enable Call Data Connector</span></span>

<span data-ttu-id="5a87f-111">Чтобы настроить и включить соединители данных вызовов, вы будете использовать следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5a87f-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="5a87f-112">Командлет</span><span class="sxs-lookup"><span data-stu-id="5a87f-112">Cmdlet</span></span>| <span data-ttu-id="5a87f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5a87f-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="5a87f-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="5a87f-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="5a87f-115">Сетевой комлет, который создает сборщик данных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5a87f-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="5a87f-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="5a87f-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="5a87f-117">Сетевой комлет, который извлекает существующий сборщик данных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5a87f-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="5a87f-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="5a87f-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="5a87f-119">Локальное решение, которое извлекает сведения о связи, созданные New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="5a87f-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="5a87f-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="5a87f-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="5a87f-121">Локальное решение, которое сохраняет локальное копирование сведений о подключении, созданных New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="5a87f-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="5a87f-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="5a87f-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="5a87f-123">Локальное поле, которое позволяет включить или отключить соединители и настроить уровень области.</span><span class="sxs-lookup"><span data-stu-id="5a87f-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="5a87f-124">Чтобы стереть конфигурацию и начать сначала, используйте cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="5a87f-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="5a87f-125">Настройка среды</span><span class="sxs-lookup"><span data-stu-id="5a87f-125">Configure your environment</span></span> 

<span data-ttu-id="5a87f-126">Чтобы настроить среду, чтобы включить онлайн-сборщик данных, сначала необходимо войти в Skype для бизнеса Online PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="5a87f-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="5a87f-127">Дополнительные сведения см. в ссылке Управление Skype для бизнеса [в Интернете с Помощью Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="5a87f-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="5a87f-128">Существует два метода входа в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5a87f-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="5a87f-129">Из оболочки управления Skype для бизнеса Server 2019 (рекомендуемый метод)</span><span class="sxs-lookup"><span data-stu-id="5a87f-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="5a87f-130">Из другого сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a87f-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="5a87f-131">Войдите в Skype для бизнеса Online PowerShell из оболочки управления Skype для бизнеса Server (рекомендуемый метод)</span><span class="sxs-lookup"><span data-stu-id="5a87f-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="5a87f-132">При первом включении соединитетеля запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5a87f-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="5a87f-133">Если вы получаете ошибку, которая уже существует, это означает, что подключение к данным вызова уже существует для клиента.</span><span class="sxs-lookup"><span data-stu-id="5a87f-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="5a87f-134">В этом случае запустите команду:</span><span class="sxs-lookup"><span data-stu-id="5a87f-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="5a87f-135">Войдите в Skype для бизнеса Online PowerShell из другого сеанса PowerShell (необязательный метод)</span><span class="sxs-lookup"><span data-stu-id="5a87f-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="5a87f-136">При первом включении соединитетеля запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5a87f-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="5a87f-137">Если вы получаете ошибку, которая уже существует, это означает, что подключение к данным вызова уже существует для клиента.</span><span class="sxs-lookup"><span data-stu-id="5a87f-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="5a87f-138">В этом случае запустите команду:</span><span class="sxs-lookup"><span data-stu-id="5a87f-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="5a87f-139">Выход вышеперечисленных команд содержит значение маркера, которое необходимо при настройке локальной среды следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5a87f-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="5a87f-140">В оболочке управления Skype для бизнеса Server укажите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5a87f-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="5a87f-141">Настройка области</span><span class="sxs-lookup"><span data-stu-id="5a87f-141">Configure the scope</span></span>

<span data-ttu-id="5a87f-142">Вы можете включить соединителя данных вызовов для определенного сайта или для всего развертывания Skype для бизнес-сервера с помощью Set-CsCloudCallDataConnectorConfiguration из оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5a87f-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="5a87f-143">Например, следующая команда позволяет подключать данные вызовов в глобальном масштабе:</span><span class="sxs-lookup"><span data-stu-id="5a87f-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="5a87f-144">В дополнение к глобальным настройкам параметры конфигурации соединители данных вызовов могут быть назначены области сайта.</span><span class="sxs-lookup"><span data-stu-id="5a87f-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="5a87f-145">Это обеспечивает дополнительную гибкость управления при мониторинге.</span><span class="sxs-lookup"><span data-stu-id="5a87f-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="5a87f-146">Например, администратор может включить переадправление соединитель данных вызовов для сайта Redmond, но отключить переадправление соединитель данных вызовов для сайта Дублина, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5a87f-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="5a87f-147">Параметры, настроенные в области сайта, имеют приоритет над настройками, настроенными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="5a87f-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="5a87f-148">Например, предположим, что переададка соединитель данных вызовов включена в глобальном масштабе, но отключена в области сайта (для сайта Redmond).</span><span class="sxs-lookup"><span data-stu-id="5a87f-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="5a87f-149">Это означает, что запись детализации вызовов и сведения о QoE не будут переададации для пользователей сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="5a87f-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="5a87f-150">Однако пользователи на других сайтах (то есть пользователи, управляемые глобальными настройками вместо параметров сайта Redmond) будут иметь запись параметров зова и переададации данных QoE.</span><span class="sxs-lookup"><span data-stu-id="5a87f-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="5a87f-151">Значения наиболее часто используемых параметров, используемых соединитетелем данных вызовов, показаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="5a87f-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="5a87f-152">Свойство</span><span class="sxs-lookup"><span data-stu-id="5a87f-152">Property</span></span>|<span data-ttu-id="5a87f-153">Описание</span><span class="sxs-lookup"><span data-stu-id="5a87f-153">Description</span></span>|<span data-ttu-id="5a87f-154">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5a87f-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a87f-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="5a87f-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="5a87f-156">Указывает, включен ли соединитатель данных вызовов.</span><span class="sxs-lookup"><span data-stu-id="5a87f-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="5a87f-157">Если true, записи мониторинга будут перенаадються в режим онлайн-мониторинга.</span><span class="sxs-lookup"><span data-stu-id="5a87f-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="5a87f-158">$False</span><span class="sxs-lookup"><span data-stu-id="5a87f-158">$False</span></span>  <br/> |
| <span data-ttu-id="5a87f-159">Идентификация</span><span class="sxs-lookup"><span data-stu-id="5a87f-159">Identity</span></span> | <span data-ttu-id="5a87f-160">Определяет уровень области для команды: глобальный или сайт.</span><span class="sxs-lookup"><span data-stu-id="5a87f-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="5a87f-161">глобальный</span><span class="sxs-lookup"><span data-stu-id="5a87f-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="5a87f-162">Отключение соединитетеля данных вызовов</span><span class="sxs-lookup"><span data-stu-id="5a87f-162">Disable Call Data Connector</span></span>

<span data-ttu-id="5a87f-163">Отключение соединителя данных вызовов не отсоединяет хранилище мониторинга от пула переднего конца и не влияет на базу данных мониторинга заднего входа.</span><span class="sxs-lookup"><span data-stu-id="5a87f-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="5a87f-164">При отключении соединители данных вызовов вы не сможете загружать данные вызовов в облако для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5a87f-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="5a87f-165">Вы отключили соединителя данных вызовов с помощью Set-CsCloudCallDataConnectorConfiguration из оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5a87f-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="5a87f-166">Например, следующая команда отключает соединитель данных вызовов в глобальной области, установив свойство EnableCallDataConnector для $False:</span><span class="sxs-lookup"><span data-stu-id="5a87f-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="5a87f-167">Если вы хотите возобновить отправку данных вызовов в облако, установите свойство EnableCallDataConnector $True, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5a87f-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="5a87f-168">Просмотр локальной информации с помощью панели мониторинга в Интернете</span><span class="sxs-lookup"><span data-stu-id="5a87f-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="5a87f-169">После включения соединиттеля данных вызовов можно просматривать данные локального вызова на панели мониторинга аналитики вызовов или панели мониторинга качества вызовов, как описано в use  [Call Analytics,](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) чтобы устранить проблемы низкого качества, включить и использовать панель мониторинга качества вызовов для Microsoft Teams и [Skype для](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)бизнеса Online .</span><span class="sxs-lookup"><span data-stu-id="5a87f-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5a87f-170">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5a87f-170">For more information</span></span>

<span data-ttu-id="5a87f-171">Дополнительные сведения о командлетах можно использовать Get-Help из командной команды Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5a87f-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5a87f-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="5a87f-172">For example:</span></span>

<span data-ttu-id="5a87f-173">Get-Help Get-CsCloudCallDataConnector | more</span><span class="sxs-lookup"><span data-stu-id="5a87f-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="5a87f-174">Get-Help Set-CsCloudCallDataConnector | more</span><span class="sxs-lookup"><span data-stu-id="5a87f-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="5a87f-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span><span class="sxs-lookup"><span data-stu-id="5a87f-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>