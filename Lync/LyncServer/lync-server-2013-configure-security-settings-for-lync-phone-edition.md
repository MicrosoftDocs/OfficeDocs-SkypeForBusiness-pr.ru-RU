---
title: 'Lync Server 2013: Настройка параметров безопасности для Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ce54b51207cc74d4ea0a57b1e66334432a6029e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="e58e9-102">Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e58e9-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e58e9-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e58e9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e58e9-104">Помогите повысить безопасность устройств с Lync Phone Edition с помощью параметров безопасности SIP и параметров блокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="e58e9-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="e58e9-105">Настройка параметров безопасности для Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="e58e9-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="e58e9-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e58e9-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e58e9-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e58e9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e58e9-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e58e9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e58e9-109">В левой панели навигации щелкните элемент **Клиенты**, а затем элемент **Конфигурация устройств**.</span><span class="sxs-lookup"><span data-stu-id="e58e9-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="e58e9-110">На странице **Конфигурация устройств** в списке конфигураций устройств дважды щелкните конфигурацию, для которой требуется изменить параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="e58e9-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="e58e9-p102">В разделе **Изменение конфигурации устройств** под заголовком **Безопасность SIP** укажите уровень безопасности SIP. По умолчанию установлен **высокий** уровень, который рекомендуется использовать.</span><span class="sxs-lookup"><span data-stu-id="e58e9-p102">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level. The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="e58e9-p103">В окне **Изменение конфигурации устройств** в разделе **Блокировка телефона** установите или снимите флажок **Активировать блокировку устройства** (установлен по умолчанию) и указать минимальную длину ПИН-кода (6 символов по умолчанию) и период времени ожидания (10 минут по умолчанию). Рекомендуется использовать эти значения по умолчанию или увеличить длину ПИН-кода и уменьшить период времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="e58e9-p103">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default). We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e58e9-115">Дополнительные сведения см <A href="lync-server-2013-enforce-phone-locking.md">в статье применение блокировки телефона в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e58e9-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e58e9-116">Настройка параметров безопасности для телефонов Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e58e9-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e58e9-117">Для управления параметрами безопасности можно использовать командную консоль Lync Server и командлет **Get – CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e58e9-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="e58e9-118">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e58e9-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e58e9-119">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="e58e9-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="e58e9-120">Изменение режима безопасности SIP</span><span class="sxs-lookup"><span data-stu-id="e58e9-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="e58e9-p105">Эта команда задает для свойства SIPSecurityMode в глобальной коллекции параметров телефона UC значение Medium. Также можно задать значение Low или High (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e58e9-p105">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium. SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="e58e9-123">Изменение минимальной длины ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="e58e9-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="e58e9-124">В этом примере параметры телефона изменяются, чтобы установить минимальную длину ПИН-кода в 7 символов.</span><span class="sxs-lookup"><span data-stu-id="e58e9-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="e58e9-125">Дополнительные сведения см. в статье [Get – CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="e58e9-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e58e9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e58e9-126">See Also</span></span>


[<span data-ttu-id="e58e9-127">Управление проверкой подлинности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e58e9-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="e58e9-128">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e58e9-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

