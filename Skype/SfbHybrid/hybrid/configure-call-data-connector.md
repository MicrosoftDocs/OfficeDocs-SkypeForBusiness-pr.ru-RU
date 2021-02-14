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
description: Инструкции по настройке соединители данных звонков, позволяющие просматривать телеметрию из локальной сети Skype для бизнеса с помощью средств Skype для бизнеса Online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726929"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="8b969-103">Настройка соединителя данных звонка</span><span class="sxs-lookup"><span data-stu-id="8b969-103">Configure Call Data Connector</span></span>

<span data-ttu-id="8b969-104">В этой статье описано, как настроить соединители данных звонков — единый набор инструментов, позволяющий просматривать данные о качестве звонков Skype для бизнеса Server с помощью панели мониторинга качества звонков Skype для бизнеса Online и средств аналитики звонков (CA).</span><span class="sxs-lookup"><span data-stu-id="8b969-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="8b969-105">Дополнительные сведения о преимуществах и предварительных требованиях соединительной связи для обработки вызовов, таких как требования к роли и настройка гибридного подключения, см. в подключении [plan Call Data Connector.](plan-call-data-connector.md)</span><span class="sxs-lookup"><span data-stu-id="8b969-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="8b969-106">Включить мониторинг</span><span class="sxs-lookup"><span data-stu-id="8b969-106">Enable Monitoring</span></span>
 
<span data-ttu-id="8b969-107">Необходимо настроить сбор данных регистрации вызовов (CDR) и качества обслуживания (QoE) в мониторинге пула переднего уровня с помощью локальных баз данных LCSCdr и QoEMetrics; в противном случае аналитика вызовов и панели мониторинга качества вызовов не будут получать данные для работы.</span><span class="sxs-lookup"><span data-stu-id="8b969-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="8b969-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span><span class="sxs-lookup"><span data-stu-id="8b969-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b969-109">Соединители данных вызовов не будут работать, если мониторинг не включен в пуле переднего входа.</span><span class="sxs-lookup"><span data-stu-id="8b969-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="8b969-110">Enable Call Data Connector</span><span class="sxs-lookup"><span data-stu-id="8b969-110">Enable Call Data Connector</span></span>

<span data-ttu-id="8b969-111">Чтобы настроить и включить соединители данных о вызовах, используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8b969-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="8b969-112">Командлет</span><span class="sxs-lookup"><span data-stu-id="8b969-112">Cmdlet</span></span>| <span data-ttu-id="8b969-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8b969-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="8b969-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="8b969-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="8b969-115">Сетевой cmdlet, который устанавливает сетевой сборщик данных.</span><span class="sxs-lookup"><span data-stu-id="8b969-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="8b969-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="8b969-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="8b969-117">Сетевой cmdlet, который извлекает существующий сетевой сборщик данных.</span><span class="sxs-lookup"><span data-stu-id="8b969-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="8b969-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8b969-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="8b969-119">Локальное решение, которое извлекает сведения о под соединении, созданные New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="8b969-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="8b969-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8b969-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="8b969-121">Локальное решение, которое сохраняет локальное копирование сведений о под подключениех, созданных New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="8b969-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="8b969-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b969-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="8b969-123">Локальное решение, позволяя включить или отключить соединители, а также настроить уровень области.</span><span class="sxs-lookup"><span data-stu-id="8b969-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="8b969-124">Чтобы стереть конфигурацию и начать заново, используйте cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="8b969-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="8b969-125">Настройка среды</span><span class="sxs-lookup"><span data-stu-id="8b969-125">Configure your environment</span></span> 

<span data-ttu-id="8b969-126">Чтобы настроить среду для сетевого сборщика данных, необходимо сначала войти в Skype для бизнеса Online PowerShell от администратора.</span><span class="sxs-lookup"><span data-stu-id="8b969-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="8b969-127">Дополнительные сведения см. в под [управлением Skype для бизнеса Online с помощью PowerShell в Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="8b969-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="8b969-128">Существует два способа входа в PowerShell в Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="8b969-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="8b969-129">Из оболочки управления Skype для бизнеса Server 2019 (рекомендуемый метод)</span><span class="sxs-lookup"><span data-stu-id="8b969-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="8b969-130">Из другого сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b969-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="8b969-131">Войдите в Skype для бизнеса Online PowerShell из оболочки управления Skype для бизнеса Server (рекомендуемый метод)</span><span class="sxs-lookup"><span data-stu-id="8b969-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="8b969-132">При первом включении соединители запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b969-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="8b969-133">Если вы получите сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="8b969-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="8b969-134">В этом случае запустите команду:</span><span class="sxs-lookup"><span data-stu-id="8b969-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="8b969-135">Войдите в Skype для бизнеса Online PowerShell из другого сеанса PowerShell (необязательный метод)</span><span class="sxs-lookup"><span data-stu-id="8b969-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="8b969-136">При первом включении соединители запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b969-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="8b969-137">Если вы получите сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="8b969-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="8b969-138">В этом случае запустите команду:</span><span class="sxs-lookup"><span data-stu-id="8b969-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="8b969-139">Выходные данные вышеперечисленных команд содержат значение маркера, которое потребуется при настройке локальной среды следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8b969-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="8b969-140">В командной оболочке Skype для бизнеса Server укажите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b969-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="8b969-141">Настройка области</span><span class="sxs-lookup"><span data-stu-id="8b969-141">Configure the scope</span></span>

<span data-ttu-id="8b969-142">Вы можете включить соединители данных звонков для определенного сайта или всего развертывания Skype для бизнеса Server с помощью Set-CsCloudCallDataConnectorConfiguration в оболочке управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8b969-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="8b969-143">Например, следующая команда включает call Data Connector в глобальной области:</span><span class="sxs-lookup"><span data-stu-id="8b969-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="8b969-144">Помимо глобальных параметров, параметры конфигурации call Data Connector можно на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="8b969-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="8b969-145">Это обеспечивает дополнительную гибкость управления, когда речь идет о мониторинге.</span><span class="sxs-lookup"><span data-stu-id="8b969-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="8b969-146">Например, администратор может включить переадправление соединители данных вызовов для сайта Redmond, но отключить переадправление call Data Connector для сайта Dublin, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8b969-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="8b969-147">Параметры, настроенные на уровне сайта, имеют приоритет над настройками, настроенными на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="8b969-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="8b969-148">Например, предположим, что переад вызов соединитель данных включен на глобальном уровне, но отключен на уровне сайта (для сайта Redmond).</span><span class="sxs-lookup"><span data-stu-id="8b969-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="8b969-149">Это означает, что регистрация вызовов и сведения о качестве вызова не будут переададации для пользователей на сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="8b969-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="8b969-150">Однако пользователи на других сайтах (то есть пользователи, управляемые глобальными настройками, а не с помощью параметров сайта Redmond) будут иметь регистрацию вызовов и перенаправят сведения о QoE.</span><span class="sxs-lookup"><span data-stu-id="8b969-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="8b969-151">Значения наиболее часто используемых параметров, используемых соединитетелем данных параметров вызова, показаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="8b969-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="8b969-152">Свойство</span><span class="sxs-lookup"><span data-stu-id="8b969-152">Property</span></span>|<span data-ttu-id="8b969-153">Описание</span><span class="sxs-lookup"><span data-stu-id="8b969-153">Description</span></span>|<span data-ttu-id="8b969-154">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8b969-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b969-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8b969-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="8b969-156">Указывает, включен ли соединител данных о вызовах.</span><span class="sxs-lookup"><span data-stu-id="8b969-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="8b969-157">Если задается true, записи мониторинга будут перенаададовы на веб-мониторинг.</span><span class="sxs-lookup"><span data-stu-id="8b969-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="8b969-158">$False</span><span class="sxs-lookup"><span data-stu-id="8b969-158">$False</span></span>  <br/> |
| <span data-ttu-id="8b969-159">Identity</span><span class="sxs-lookup"><span data-stu-id="8b969-159">Identity</span></span> | <span data-ttu-id="8b969-160">Определяет уровень области для команды: глобальный или сайт.</span><span class="sxs-lookup"><span data-stu-id="8b969-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="8b969-161">global</span><span class="sxs-lookup"><span data-stu-id="8b969-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="8b969-162">Отключение соединители данных о вызовах</span><span class="sxs-lookup"><span data-stu-id="8b969-162">Disable Call Data Connector</span></span>

<span data-ttu-id="8b969-163">Отключение соединителя данных о вызовах не отключает хранилище мониторинга от пула переднего входа и не делает его удалить или иным образом влиять на базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="8b969-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="8b969-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span><span class="sxs-lookup"><span data-stu-id="8b969-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="8b969-165">Соединители данных звонков отключаются с помощью Set-CsCloudCallDataConnectorConfiguration в оболочке управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8b969-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="8b969-166">Например, следующая команда отключает call Data Connector на глобальном уровне, задав для свойства EnableCallDataConnector $False:</span><span class="sxs-lookup"><span data-stu-id="8b969-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="8b969-167">Чтобы возобновить отправку данных о вызовах в облако, установите для свойства EnableCallDataConnector $True, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8b969-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="8b969-168">Просмотр локальной информации с помощью информационной панели в Интернете</span><span class="sxs-lookup"><span data-stu-id="8b969-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="8b969-169">После включения соединители данных о вызовах вы можете просматривать данные о локальном звонке на [](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) информационной панели аналитики звонков или панели мониторинга качества звонков, как описано в описании использования аналитики звонков для устранения неполадок с неудовлетворительной качеством и включения и использования панели мониторинга качества звонков для Microsoft Teams и [Skype для бизнеса Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="8b969-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8b969-170">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8b969-170">For more information</span></span>

<span data-ttu-id="8b969-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8b969-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8b969-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="8b969-172">For example:</span></span>

<span data-ttu-id="8b969-173">Get-Help Get-CsCloudCallDataConnector | more</span><span class="sxs-lookup"><span data-stu-id="8b969-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="8b969-174">Get-Help Set-CsCloudCallDataConnector | more</span><span class="sxs-lookup"><span data-stu-id="8b969-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="8b969-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span><span class="sxs-lookup"><span data-stu-id="8b969-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
