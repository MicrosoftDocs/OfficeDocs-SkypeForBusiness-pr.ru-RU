---
title: Управление сетевыми регионами
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Область сети* — это сетевые концентраторы или магистрали, используемые в конфигурации управления приемом вызовов, E9-1-1 и обхода мультимедиа.
ms.openlocfilehash: 2020eea2cf8bf85c915ebf88de6f86cb3a0ee9ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122453"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="a4290-103">Управление областями сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a4290-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="a4290-104">*Области сети* представляют собой сетевые концентраторы или магистрали, используемые в конфигурации контроля допуска звонков, E9-1-1 и обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a4290-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="a4290-105">Следующие процедуры используются для просмотра, создания или изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="a4290-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="a4290-106">Например, если области сети уже созданы для одного из компонентов голосовой связи, новые области сети создавать не требуется; остальные расширенные компоненты корпоративной голосовой связи используют те же области сети.</span><span class="sxs-lookup"><span data-stu-id="a4290-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="a4290-107">Тем не менее, возможно, потребуется изменить существующее определение области сети, чтобы применить специальные настройки для конкретных компонентов.</span><span class="sxs-lookup"><span data-stu-id="a4290-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="a4290-108">Например, когда после создания областей сети для системы E9-1-1 (которой не требуется связанный центральный сайт) выполняется развертывание системы контроля допуска звонков, потребуется изменить определения области сети для указания центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="a4290-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="a4290-109">Используйте процедуры в этой статье для просмотра сведений о сетевом регионе или создания, изменения или удаления сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="a4290-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="a4290-110">Просмотр сведений о сетевом регионе</span><span class="sxs-lookup"><span data-stu-id="a4290-110">View network region information</span></span> 


<span data-ttu-id="a4290-111">Область сети связывает части сети, расположенные в различных географических районах.</span><span class="sxs-lookup"><span data-stu-id="a4290-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a4290-112">Каждый регион сети должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="a4290-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a4290-113">Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="a4290-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a4290-114">Панель управления Skype для бизнес-серверов можно использовать для просмотра сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="a4290-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="a4290-115">Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="a4290-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a4290-116">Используйте эту тему для просмотра существующих сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="a4290-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="a4290-117">Просмотр сведений о сетевом регионе с панелью управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="a4290-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a4290-118">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a4290-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a4290-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a4290-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a4290-120">В левой панели навигации нажмите **кнопку Конфигурация сети,** а затем щелкните **Регион**.</span><span class="sxs-lookup"><span data-stu-id="a4290-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a4290-121">На странице **Регион** щелкните регион, который следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="a4290-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="a4290-122">одновременно можно просматривать только один регион.</span><span class="sxs-lookup"><span data-stu-id="a4290-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="a4290-123">В меню **Изменить** щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a4290-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a4290-124">Просмотр сведений о сетевом регионе с помощью Windows PowerShell-кодлетов</span><span class="sxs-lookup"><span data-stu-id="a4290-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a4290-125">Сведения о сетевом регионе можно просматривать с помощью Windows PowerShell **и командлета Get-CsNetworkRegion.**</span><span class="sxs-lookup"><span data-stu-id="a4290-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="a4290-126">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4290-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="a4290-127">Просмотр сведений о сетевом регионе</span><span class="sxs-lookup"><span data-stu-id="a4290-127">To view network region information</span></span>

  - <span data-ttu-id="a4290-128">Чтобы просмотреть сведения обо всех регионах сети, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="a4290-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="a4290-129">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="a4290-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="a4290-130">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="a4290-130">For more information, see the help topic for the [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="a4290-131">Создание или изменение сетевых регионов</span><span class="sxs-lookup"><span data-stu-id="a4290-131">Create or modify network regions</span></span> 

<span data-ttu-id="a4290-132">Область сети связывает части сети, расположенные в различных географических районах.</span><span class="sxs-lookup"><span data-stu-id="a4290-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a4290-133">Каждый регион сети должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="a4290-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a4290-134">Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="a4290-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a4290-135">Панель управления серверами Skype для бизнеса можно настроить сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="a4290-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="a4290-136">Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="a4290-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a4290-137">С панели управления Skype для бизнес-серверов можно создать, изменить или удалить сетевой регион.</span><span class="sxs-lookup"><span data-stu-id="a4290-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="a4290-138">Используйте этот раздел для создания и изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="a4290-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="a4290-139">Создание области сети</span><span class="sxs-lookup"><span data-stu-id="a4290-139">To create a network region</span></span>

1.  <span data-ttu-id="a4290-140">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a4290-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a4290-141">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a4290-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a4290-142">В левой панели навигации нажмите **кнопку Конфигурация сети,** а затем щелкните **Регион**.</span><span class="sxs-lookup"><span data-stu-id="a4290-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a4290-143">На странице **Область**  щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a4290-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="a4290-144">На странице **Создание области** введите имя области сети в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="a4290-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="a4290-145">Это значение должно быть уникальным в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a4290-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="a4290-146">В раскрывающемся списке **Центральный сайт** выберите центральный сайт для этой области сети.</span><span class="sxs-lookup"><span data-stu-id="a4290-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="a4290-p106">Флажок **Включить альтернативный путь для звонков** установлен по умолчанию. Этот параметр указывает, будут ли звонки перенаправляться по альтернативному пути, если пропускной способности основного пути недостаточно. Этот флажок нужно снимать только в том случае, если требуется отключить разгрузку в Интернет. При наличии звонков по Интернету этот флажок должен быть установлен независимо от параметров пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a4290-p106">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="a4290-p107">Флажок **Включить альтернативный путь видеозвонков** установлен по умолчанию. Этот параметр указывает, будут ли видеозвонки перенаправляться по альтернативному пути, если пропускной способности основного пути недостаточно. Этот флажок нужно снимать только в том случае, если требуется отключить разгрузку в Интернет. При наличии звонков по Интернету этот флажок должен быть установлен независимо от параметров пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a4290-p107">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="a4290-155">Введите дополнительные сведения об области сети в поле **Описание** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="a4290-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="a4290-156">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="a4290-156">Click **Commit**.</span></span>

<span data-ttu-id="a4290-157">При создании области сети таблица **Связанные сайты** не используется.</span><span class="sxs-lookup"><span data-stu-id="a4290-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="a4290-158">Вы можете связать сайт с областью при создании или изменении сайта.</span><span class="sxs-lookup"><span data-stu-id="a4290-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="a4290-159">Подробные сведения см. [в материале Управление управлением управлением приемом вызовов для сайтов.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="a4290-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="a4290-160">Изменение области сети</span><span class="sxs-lookup"><span data-stu-id="a4290-160">To modify a network region</span></span>

1.  <span data-ttu-id="a4290-161">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a4290-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a4290-162">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a4290-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a4290-163">В левой панели навигации нажмите **кнопку Конфигурация сети,** а затем щелкните **Регион**.</span><span class="sxs-lookup"><span data-stu-id="a4290-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a4290-164">На странице **Область** щелкните область, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="a4290-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="a4290-165">В меню **Правка** выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a4290-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a4290-166">На странице **Изменение области** можно изменить параметры включения и отключения альтернативных путей для звонков и видеозвонков, а также изменить описание (дополнительные сведения см. в подразделе "Создание области сети" настоящего раздела).</span><span class="sxs-lookup"><span data-stu-id="a4290-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="a4290-167">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="a4290-167">Click **Commit**.</span></span>

<span data-ttu-id="a4290-p109">На этой странице нельзя изменить **Связанные сайты**. В этом списке указаны сайты, на которые может повлиять изменение параметров области.</span><span class="sxs-lookup"><span data-stu-id="a4290-p109">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="a4290-170">Удаление существующих сетевых регионов</span><span class="sxs-lookup"><span data-stu-id="a4290-170">Delete existing network regions</span></span> 

<span data-ttu-id="a4290-171">Область сети связывает части сети, расположенные в различных географических районах.</span><span class="sxs-lookup"><span data-stu-id="a4290-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a4290-172">Каждый регион сети должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="a4290-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a4290-173">Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="a4290-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a4290-174">Панель управления серверами Skype для бизнеса можно настроить сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="a4290-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="a4290-175">Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="a4290-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a4290-176">С панели управления Skype для бизнес-серверов можно создать, изменить или удалить сетевой регион.</span><span class="sxs-lookup"><span data-stu-id="a4290-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="a4290-177">Используйте этот раздел для удаления существующих областей сети.</span><span class="sxs-lookup"><span data-stu-id="a4290-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="a4290-178">Удаление области сети</span><span class="sxs-lookup"><span data-stu-id="a4290-178">To delete a network region</span></span>

1.  <span data-ttu-id="a4290-179">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a4290-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a4290-180">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a4290-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a4290-181">В левой панели навигации нажмите **кнопку Конфигурация сети,** а затем щелкните **Регион**.</span><span class="sxs-lookup"><span data-stu-id="a4290-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="a4290-182">На странице **областей** щелкните область, которую следует удалить.</span><span class="sxs-lookup"><span data-stu-id="a4290-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="a4290-p111">Можно одновременно удалять несколько областей. Для этого нажмите клавишу CTRL и выберите несколько областей, удерживая клавишу CTRL нажатой. Можно также выбрать все области, нажав пункт **Выбрать все** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="a4290-p111">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="a4290-186">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a4290-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="a4290-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a4290-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="a4290-188">Нельзя удалить область сети, если она связана с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="a4290-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="a4290-189">При попытке удалить область, связанную с сайтом, вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a4290-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="a4290-190">Чтобы увидеть, связана ли область с какими-либо сайтами, выделите эту область и выберите команду **Показать подробности** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="a4290-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="a4290-191">См. также</span><span class="sxs-lookup"><span data-stu-id="a4290-191">See Also</span></span>

[<span data-ttu-id="a4290-192">Управление маршрутами регионов сети</span><span class="sxs-lookup"><span data-stu-id="a4290-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="a4290-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a4290-193">New-CsNetworkRegion</span></span>](/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="a4290-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a4290-194">Set-CsNetworkRegion</span></span>](/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="a4290-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a4290-195">Remove-CsNetworkRegion</span></span>](/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="a4290-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a4290-196">Get-CsNetworkRegion</span></span>](/powershell/module/skype/Get-CsNetworkRegionLink)