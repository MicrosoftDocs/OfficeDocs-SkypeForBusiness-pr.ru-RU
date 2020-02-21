---
title: Удаление существующей коллекции параметров конфигурации Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5c601726cfc18d230519741ebcc7561da54d73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ee6cc-102">Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee6cc-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee6cc-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ee6cc-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ee6cc-104">Если вы больше не хотите использовать набор параметров для устройств с Lync Phone Edition, удалите его.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="ee6cc-105">Если вы удалите коллекцию для сайта, глобальные параметры будут применяться к телефонам на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="ee6cc-106">Вы не можете удалить глобальную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ee6cc-107">Вместо удаления коллекции может потребоваться изменить некоторые параметры.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="ee6cc-108">Сведения о том, как это сделать, можно найти <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">в статье Создание или изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="ee6cc-109">Удаление коллекции параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ee6cc-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="ee6cc-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ee6cc-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ee6cc-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ee6cc-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ee6cc-113">На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Настройки устройств**.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="ee6cc-114">На странице " **Конфигурация устройства** " щелкните удаляемую коллекцию, а затем выберите команду **Удалить**в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="ee6cc-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ee6cc-115">Если вы удаляете глобальную коллекцию, параметры просто возвращаются к параметрам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="ee6cc-116">Коллекция не отключается.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="ee6cc-117">В окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ee6cc-118">Удаление параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee6cc-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ee6cc-119">Параметры конфигурации Lync Phone Edition можно удалить с помощью Windows PowerShell и командлета **Remove – ксукконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="ee6cc-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="ee6cc-120">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ee6cc-121">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="ee6cc-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="ee6cc-122">Удаление указанной коллекции параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ee6cc-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="ee6cc-123">Эта команда удаляет параметры конфигурации телефона UC, применяемые к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="ee6cc-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="ee6cc-124">Удаление всех параметров конфигурации Lync Phone Edition, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="ee6cc-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="ee6cc-125">Эта команда удаляет все параметры конфигурации телефона UC, применяемые к области службы:</span><span class="sxs-lookup"><span data-stu-id="ee6cc-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="ee6cc-126">Удаление всех параметров конфигурации Lync Phone Edition, в которых отключена Блокировка телефона</span><span class="sxs-lookup"><span data-stu-id="ee6cc-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="ee6cc-127">Эта команда удаляет любую коллекцию параметров конфигурации телефона UC, в которых отключена Блокировка телефона:</span><span class="sxs-lookup"><span data-stu-id="ee6cc-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="ee6cc-128">Дополнительные сведения см. в разделе [Remove – CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="ee6cc-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

