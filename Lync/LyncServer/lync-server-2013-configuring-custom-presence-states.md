---
title: 'Lync Server 2013: Настройка настраиваемых состояний присутствия'
description: 'Lync Server 2013: Настройка настраиваемых состояний присутствия.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b277f096ff17ffa63615468ac9b4f21dead68e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557975"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="d762f-103">Настройка настраиваемых состояний присутствия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d762f-103">Configuring custom presence states in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d762f-104">_**Последнее изменение темы:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="d762f-104">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="d762f-105">Чтобы определить настраиваемые состояния присутствия в Lync 2013, создайте файл настраиваемой конфигурации сведений о присутствии XML, а затем укажите его расположение с помощью командлетов командной консоли Lync Server **New-CSClientPolicy** или **Set-CSClientPolicy** с параметром кустомстатеурл.</span><span class="sxs-lookup"><span data-stu-id="d762f-105">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="d762f-106">Файлы конфигурации имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="d762f-106">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="d762f-107">Настраиваемые состояния присутствия можно настроить с индикаторами присутствия "доступно", "занято" и "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="d762f-107">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="d762f-108">Атрибут Availability определяет, какой индикатор присутствия связан с текстом состояния настраиваемого состояния.</span><span class="sxs-lookup"><span data-stu-id="d762f-108">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="d762f-109">В примере ниже в этом разделе текст состояния, работающий с домашней страницы, отображается справа от индикатора присутствия зеленого (доступного) индикатора присутствия.</span><span class="sxs-lookup"><span data-stu-id="d762f-109">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="d762f-110">Максимальная длина текста состояния — 64 символов.</span><span class="sxs-lookup"><span data-stu-id="d762f-110">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="d762f-111">Можно добавить не более четырех настраиваемых состояний присутствия.</span><span class="sxs-lookup"><span data-stu-id="d762f-111">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="d762f-112">Параметр Кустомстатеурл указывает расположение файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d762f-112">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="d762f-113">В Lync 2013 режим высокой безопасности SIP включен по умолчанию, поэтому необходимо хранить пользовательский файл конфигурации присутствия на веб-сервере с включенным протоколом HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d762f-113">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="d762f-114">В противном случае Lync 2013 клиенты не смогут подключаться к нему.</span><span class="sxs-lookup"><span data-stu-id="d762f-114">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="d762f-115">Например, допустимым адресом является `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` .</span><span class="sxs-lookup"><span data-stu-id="d762f-115">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d762f-116">Хотя это не рекомендуется в рабочей среде, вы можете протестировать файл конфигурации, расположенный на общем файловом ресурсе, с помощью параметра реестра EnableSIPHighSecurityMode, чтобы отключить режим высокой безопасности SIP на клиенте.</span><span class="sxs-lookup"><span data-stu-id="d762f-116">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="d762f-117">Затем можно использовать параметр реестра Кустомстатеурл, чтобы указать расположение для файла конфигурации, отличное от HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d762f-117">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="d762f-118">Обратите внимание, что в Lync 2013 учитываются параметры реестра Lync 2010, но куст реестра обновлен.</span><span class="sxs-lookup"><span data-stu-id="d762f-118">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="d762f-119">Вы создадите параметры реестра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d762f-119">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d762f-120">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="d762f-120">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="d762f-121">Тип: DWORD</span><span class="sxs-lookup"><span data-stu-id="d762f-121">Type: DWORD</span></span></P>
> <P><span data-ttu-id="d762f-122">Данные значения: 0</span><span class="sxs-lookup"><span data-stu-id="d762f-122">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="d762f-123">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="d762f-123">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="d762f-124">Тип: строка (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="d762f-124">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="d762f-125">Data value (примеры): file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml или file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="d762f-125">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="d762f-126">Локализовать пользовательское состояние присутствия, указав одну или несколько схем ИДЕНТИФИКАТОРов языковых стандартов (LCID) в XML-файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d762f-126">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="d762f-127">В примере далее в этом разделе показано локализация на английский (США), Норвежский (1033), Норвежский (1044), французский (США), французский (1055) (1036) и Турецкий ().</span><span class="sxs-lookup"><span data-stu-id="d762f-127">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="d762f-128">Список LCID можно узнать в статье Языковые идентификаторы, назначенные корпорацией Майкрософт по адресу <https://go.microsoft.com/fwlink/p/?linkid=157331> .</span><span class="sxs-lookup"><span data-stu-id="d762f-128">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="d762f-129">Добавление настраиваемых состояний присутствия в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d762f-129">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="d762f-130">Создайте XML-файл конфигурации, в котором используется формат следующего примера:</span><span class="sxs-lookup"><span data-stu-id="d762f-130">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="d762f-131">Сохраните XML-файл конфигурации на веб-сервере с включенной поддержкой протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d762f-131">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="d762f-132">В этом примере файл называется Presence.xml и сохраняется в расположении https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml .</span><span class="sxs-lookup"><span data-stu-id="d762f-132">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="d762f-133">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d762f-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="d762f-134">В командной консоли Lync Server определите расположение XML-файла конфигурации с помощью команды, аналогичной следующей:</span><span class="sxs-lookup"><span data-stu-id="d762f-134">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="d762f-135">Используйте командлет **Grant – CSClientPolicy** для назначения этой новой политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="d762f-135">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="d762f-136">Дополнительные сведения см. в статье [New/CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и [Grant – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d762f-136">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="d762f-137">По умолчанию Lync Server 2013 &nbsp; обновляет политики клиентов и параметры каждые три часа.</span><span class="sxs-lookup"><span data-stu-id="d762f-137">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="d762f-138">Если вы хотите продолжить использование параметров групповой политики из предыдущих выпусков, таких как Кустомстатеурл, Lync 2013 будет распознавать параметры, если они находятся в кусте реестра New Policy (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span><span class="sxs-lookup"><span data-stu-id="d762f-138">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="d762f-139">Тем не менее, приоритет имеют серверные политики клиентов.</span><span class="sxs-lookup"><span data-stu-id="d762f-139">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

