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
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="8af57-102">Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8af57-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8af57-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8af57-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8af57-104">Улучшите безопасность устройств с Lync Phone Edition, используя настройки безопасности SIP и параметры блокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="8af57-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="8af57-105">Настройка параметров безопасности для Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8af57-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="8af57-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8af57-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8af57-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8af57-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8af57-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8af57-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8af57-109">На панели навигации слева выберите пункт **Клиенты**, а затем — **Конфигурация устройства**.</span><span class="sxs-lookup"><span data-stu-id="8af57-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="8af57-110">На странице **Конфигурация устройства** в списке конфигураций устройств дважды щелкните конфигурацию, для которой вы хотите изменить параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="8af57-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="8af57-111">В разделе **изменение конфигурации устройства**в **системе безопасности SIP**укажите уровень безопасности SIP.</span><span class="sxs-lookup"><span data-stu-id="8af57-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="8af57-112">Уровень по умолчанию — **High**, поэтому мы рекомендуем использовать.</span><span class="sxs-lookup"><span data-stu-id="8af57-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="8af57-113">В диалоговом окне **изменение конфигурации устройства**в разделе **Блокировка телефона**установите или снимите флажок **Принудительная Блокировка устройства** (выбрано по умолчанию) и укажите минимальную длину PIN-кода (по умолчанию) и период ожидания (по умолчанию — по 5 минутам).</span><span class="sxs-lookup"><span data-stu-id="8af57-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="8af57-114">Мы рекомендуем использовать эти значения по умолчанию или увеличив длину PIN-кода и (или) уменьшить период ожидания.</span><span class="sxs-lookup"><span data-stu-id="8af57-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8af57-115">Подробнее смотрите в разделе <A href="lync-server-2013-enforce-phone-locking.md">принудительное использование блокировки телефона в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8af57-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8af57-116">Настройка параметров безопасности для телефонов Lync Phone Edition с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8af57-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8af57-117">Параметры безопасности можно управлять с помощью командной консоли Lync Server Management Shell и командлета **Get-ксукфонеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="8af57-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="8af57-118">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8af57-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8af57-119">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8af57-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="8af57-120">Изменение режима безопасности SIP</span><span class="sxs-lookup"><span data-stu-id="8af57-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="8af57-121">Эта команда задает средний уровень Сипсекуритимоде для глобальной коллекции параметров телефонной связи UC.</span><span class="sxs-lookup"><span data-stu-id="8af57-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="8af57-122">Также можно установить низкий или высокий уровень безопасности SIP (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8af57-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="8af57-123">Изменение минимальной длины PIN-кода</span><span class="sxs-lookup"><span data-stu-id="8af57-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="8af57-124">В этом примере все параметры телефонной связи по УНИКАЛЬности изменяются для использования минимальной длины в 7 цифр.</span><span class="sxs-lookup"><span data-stu-id="8af57-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="8af57-125">Подробности можно найти в [статьях Get-ксукфонеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8af57-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8af57-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8af57-126">See Also</span></span>


[<span data-ttu-id="8af57-127">Управление проверкой подлинности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8af57-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="8af57-128">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8af57-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

