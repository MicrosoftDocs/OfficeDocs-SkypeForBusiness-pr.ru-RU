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
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="553be-102">Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="553be-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="553be-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="553be-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="553be-104">Если вы больше не хотите использовать коллекцию параметров для устройств с Lync Phone Edition, удалите ее.</span><span class="sxs-lookup"><span data-stu-id="553be-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="553be-105">Если вы удалите коллекцию для сайта, глобальные параметры будут применены к телефонам на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="553be-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="553be-106">Вы не можете удалить глобальную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="553be-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="553be-107">Вместо удаления коллекции, возможно, потребуется изменить некоторые параметры.</span><span class="sxs-lookup"><span data-stu-id="553be-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="553be-108">Подробнее о том, как это сделать, можно найти <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">в разделе Создание или изменение семейства параметров конфигурации Lync Phone Edition в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="553be-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="553be-109">Удаление коллекции параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="553be-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="553be-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="553be-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="553be-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="553be-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="553be-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="553be-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="553be-113">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации устройства** .</span><span class="sxs-lookup"><span data-stu-id="553be-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="553be-114">На странице **Конфигурация устройства** выберите коллекцию, которую вы хотите удалить, а затем в меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="553be-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="553be-115">Если вы удалите глобальную коллекцию, для параметров будет восстановлены параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="553be-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="553be-116">Коллекция не выходит за края.</span><span class="sxs-lookup"><span data-stu-id="553be-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="553be-117">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="553be-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="553be-118">Удаление параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="553be-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="553be-119">Вы можете удалить параметры конфигурации Lync Phone Edition с помощью Windows PowerShell и командлета **Remove-ксукконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="553be-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="553be-120">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="553be-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="553be-121">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="553be-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="553be-122">Удаление заданной коллекции параметров конфигурации Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="553be-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="553be-123">Эта команда удаляет параметры конфигурации телефона UC, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="553be-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="553be-124">Удаление всех параметров конфигурации Lync Phone Edition, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="553be-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="553be-125">Эта команда удаляет все параметры конфигурации телефона UC, примененные к области действия службы.</span><span class="sxs-lookup"><span data-stu-id="553be-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="553be-126">Удаление всех параметров конфигурации Lync Phone Edition с отключенной блокировкой телефона</span><span class="sxs-lookup"><span data-stu-id="553be-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="553be-127">Эта команда удаляет все наборы параметров конфигурации телефона UC, в которых заблокирована телефонная блокировка.</span><span class="sxs-lookup"><span data-stu-id="553be-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="553be-128">Подробности можно найти в разделе [Remove-ксукфонеконфигуратион](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="553be-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

