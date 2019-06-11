---
title: 'Lync Server 2013: Настройка настраиваемых состояний присутствия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12083d1895f8e5191f15b43efaf2835faecdb5ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="6903b-102">Настройка настраиваемых состояний присутствия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6903b-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6903b-103">_**Тема последнего изменения:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="6903b-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="6903b-104">Для определения настраиваемых состояний присутствия в Lync 2013 создайте настраиваемый XML-файл конфигурации присутствия и укажите его расположение с помощью командлетов командной консоли Lync Server **New-CSClientPolicy** или **Set-CSClientPolicy** с параметром Кустомстатеурл.</span><span class="sxs-lookup"><span data-stu-id="6903b-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="6903b-105">Файлы конфигурации обладают следующими свойствами:</span><span class="sxs-lookup"><span data-stu-id="6903b-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="6903b-106">Настраиваемые состояния присутствия можно настроить с индикаторами присутствия "доступно", "занят" и "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="6903b-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="6903b-107">Атрибут доступности определяет, какой индикатор присутствия связан с текстом состояния для настраиваемого состояния.</span><span class="sxs-lookup"><span data-stu-id="6903b-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="6903b-108">В примере ниже в этом разделе текст состояния, работающий из дома, отображается справа от зеленого (доступного) индикатора присутствия.</span><span class="sxs-lookup"><span data-stu-id="6903b-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="6903b-109">Максимальная длина текста состояния составляет 64 символов.</span><span class="sxs-lookup"><span data-stu-id="6903b-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="6903b-110">Можно добавить не более четырех настраиваемых состояний присутствия.</span><span class="sxs-lookup"><span data-stu-id="6903b-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="6903b-111">Параметр Кустомстатеурл указывает расположение файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6903b-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="6903b-112">В Lync 2013 режим высокой безопасности SIP включен по умолчанию, поэтому необходимо сохранить настраиваемый файл конфигурации присутствия на веб-сервере с включенным HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6903b-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="6903b-113">В противном случае пользователи Lync 2013 не смогут подключиться к нему.</span><span class="sxs-lookup"><span data-stu-id="6903b-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="6903b-114">Например, допустимый адрес `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span><span class="sxs-lookup"><span data-stu-id="6903b-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6903b-115">Несмотря на то, что его не рекомендуется использовать в производственной среде, вы можете протестировать файл конфигурации, расположенный на общем файловом адресе (не HTTPS), с помощью параметра реестра Енаблесифигхсекуритимоде, чтобы отключить режим высокой безопасности SIP на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="6903b-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="6903b-116">Затем вы можете использовать параметр реестра Кустомстатеурл, чтобы указать расположение для файла конфигурации, отличное от HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6903b-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="6903b-117">Обратите внимание, что в Lync 2013 учитываются параметры реестра Lync 2010, но куст реестра обновлен.</span><span class="sxs-lookup"><span data-stu-id="6903b-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="6903b-118">Вы можете создать параметры реестра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6903b-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6903b-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="6903b-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="6903b-120">Type (тип): DWORD</span><span class="sxs-lookup"><span data-stu-id="6903b-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="6903b-121">Данные значения: 0</span><span class="sxs-lookup"><span data-stu-id="6903b-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="6903b-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="6903b-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="6903b-123">Тип: строка (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="6903b-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="6903b-124">Данные значения (примеры): file://\\лспул. Corp. contoso. ком\лсфилешаре\клиентконфигфолдер\пресенце.ксмл или file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</span><span class="sxs-lookup"><span data-stu-id="6903b-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="6903b-125">Локализовать свое собственное состояние присутствия, указав одну или несколько схем ИДЕНТИФИКАТОРов языков (LCID) в XML-файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6903b-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="6903b-126">В примере ниже показана локализация на английский (США) (1033), Норвежский (букмол, 1044), французский (Франция) (1036) и на турецком (1055).</span><span class="sxs-lookup"><span data-stu-id="6903b-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="6903b-127">Список LCID можно найти в <http://go.microsoft.com/fwlink/p/?linkid=157331>разделе Коды языков, назначенные корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6903b-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="6903b-128">Добавление настраиваемых состояний присутствия в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6903b-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="6903b-129">Создайте XML-файл конфигурации, в котором используется формат следующего примера:</span><span class="sxs-lookup"><span data-stu-id="6903b-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
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

2.  <span data-ttu-id="6903b-130">Сохраните файл конфигурации XML на веб-сервере с включенным HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6903b-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="6903b-131">В этом примере файл имеет имя presence. XML и сохранен в указанном расположении https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span><span class="sxs-lookup"><span data-stu-id="6903b-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="6903b-132">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6903b-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="6903b-133">В командной консоли Lync Server укажите расположение XML-файла конфигурации, выполнив команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="6903b-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="6903b-134">С помощью командлета **Grant-CSClientPolicy** можно назначить пользователям новую политику.</span><span class="sxs-lookup"><span data-stu-id="6903b-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="6903b-135">Подробные сведения можно найти в разделе [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6903b-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="6903b-136">По умолчанию Lync Server 2013&nbsp;обновляет политики клиентов и параметры каждые три часа.</span><span class="sxs-lookup"><span data-stu-id="6903b-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="6903b-137">Если вы хотите продолжить использовать параметры групповой политики из предыдущих выпусков, например Кустомстатеурл, Lync 2013 будет распознавать параметры, если они находятся в новом кусте реестра (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span><span class="sxs-lookup"><span data-stu-id="6903b-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="6903b-138">Тем не менее, приоритетом обладают серверные политики на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="6903b-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

