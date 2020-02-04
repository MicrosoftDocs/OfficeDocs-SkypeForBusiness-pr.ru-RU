---
title: 'Lync Server 2013: принудительное использование блокировки телефона'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="1aa8f-102">Принудительная Блокировка телефона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa8f-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aa8f-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1aa8f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1aa8f-104">Устройства Lync Phone Edition можно блокировать в целях обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="1aa8f-105">Если вы используете блокировку телефона, устройство с Lync Phone Edition блокируется по истечении определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="1aa8f-106">Когда телефон заблокирован, пользователь может звонить, но не может получить доступ к календарю, контактной информации, голосовой почте или звонкам либо использовать функцию поиска.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="1aa8f-107">Чтобы разблокировать телефон, пользователь введет PIN-код.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="1aa8f-108">Для принудительного включения блокировки на телефоне включите и настройте ее с помощью панели управления Lync Server или командлетов Lync Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="1aa8f-109">Вы можете включить блокировку на телефоне глобально или только на сайте, для которого она настроена.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="1aa8f-110">Настройка и принудительное использование блокировки телефона</span><span class="sxs-lookup"><span data-stu-id="1aa8f-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="1aa8f-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1aa8f-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1aa8f-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1aa8f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1aa8f-114">Нажмите **Клиенты**и выберите **Конфигурация устройства**.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="1aa8f-115">На вкладке **Конфигурация устройства** в списке конфигураций устройств дважды щелкните конфигурацию, для которой вы хотите изменить параметры блокировки телефона.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="1aa8f-116">В диалоговом окне **изменение конфигурации устройства** убедитесь, что установлен флажок **Принудительная Блокировка устройства** .</span><span class="sxs-lookup"><span data-stu-id="1aa8f-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="1aa8f-117">В поле **Минимальная длина ПИН-кода**введите значение по умолчанию для минимального числа цифр, которые должен содержать ПИН-код для разблокировки, или укажите новое значение.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="1aa8f-118">Диапазон длины PIN-кода состоит из 4 – 15 цифр, а значение по умолчанию — Six.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="1aa8f-119">В параметрах времени ожидания для **телефонного закрепления**введите значение по умолчанию для минимальной продолжительности времени, по истечении которого блокируется Телефон, или укажите новое значение.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="1aa8f-120">Диапазон времени ожидания равен от 0 до 60 минут, а значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="1aa8f-121">Введите значение в формате чч: мм: СС.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="1aa8f-122">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1aa8f-123">Принудительная Блокировка телефона с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1aa8f-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1aa8f-124">С помощью командлета Set-Ксукфонеконфигуратион можно принудительно использовать блокировку телефона.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="1aa8f-125">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1aa8f-126">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="1aa8f-127">Включение блокировки телефона</span><span class="sxs-lookup"><span data-stu-id="1aa8f-127">To enable phone locking</span></span>

  - <span data-ttu-id="1aa8f-128">Следующая команда включает блокировку на телефоне для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="1aa8f-129">Чтобы отключить блокировку на телефоне, установите для свойства Енфорцефонелокк значение false ($False).</span><span class="sxs-lookup"><span data-stu-id="1aa8f-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="1aa8f-130">Включение блокировки телефона и изменение времени ожидания блокировки телефона</span><span class="sxs-lookup"><span data-stu-id="1aa8f-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="1aa8f-131">Эта команда включает блокировку телефона, а также задает время ожидания блокировки в 30 минут.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="1aa8f-132">Включение блокировки телефона в рамках всей Организации</span><span class="sxs-lookup"><span data-stu-id="1aa8f-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="1aa8f-133">В этом примере функция блокировки телефона включена для всех параметров конфигурации телефона UC, используемых в Организации.</span><span class="sxs-lookup"><span data-stu-id="1aa8f-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="1aa8f-134">Дополнительные сведения можно найти в разделе справки по командлету [Set-ксукфонеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1aa8f-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1aa8f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="1aa8f-135">See Also</span></span>


[<span data-ttu-id="1aa8f-136">Управление проверкой подлинности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa8f-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="1aa8f-137">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa8f-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

