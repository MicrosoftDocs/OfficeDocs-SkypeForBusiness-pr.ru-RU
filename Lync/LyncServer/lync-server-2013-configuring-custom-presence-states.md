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

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Настройка настраиваемых состояний присутствия в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-10_

Для определения настраиваемых состояний присутствия в Lync 2013 создайте настраиваемый XML-файл конфигурации присутствия и укажите его расположение с помощью командлетов командной консоли Lync Server **New-CSClientPolicy** или **Set-CSClientPolicy** с параметром Кустомстатеурл.

Файлы конфигурации обладают следующими свойствами:

  - Настраиваемые состояния присутствия можно настроить с индикаторами присутствия "доступно", "занят" и "не беспокоить".

  - Атрибут доступности определяет, какой индикатор присутствия связан с текстом состояния для настраиваемого состояния. В примере ниже в этом разделе текст состояния, работающий из дома, отображается справа от зеленого (доступного) индикатора присутствия.

  - Максимальная длина текста состояния составляет 64 символов.

  - Можно добавить не более четырех настраиваемых состояний присутствия.

  - Параметр Кустомстатеурл указывает расположение файла конфигурации. В Lync 2013 режим высокой безопасности SIP включен по умолчанию, поэтому необходимо сохранить настраиваемый файл конфигурации присутствия на веб-сервере с включенным HTTPS. В противном случае пользователи Lync 2013 не смогут подключиться к нему. Например, допустимый адрес `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<div>


> [!NOTE]  
> Несмотря на то, что его не рекомендуется использовать в производственной среде, вы можете протестировать файл конфигурации, расположенный на общем файловом адресе (не HTTPS), с помощью параметра реестра Енаблесифигхсекуритимоде, чтобы отключить режим высокой безопасности SIP на клиентском компьютере. Затем вы можете использовать параметр реестра Кустомстатеурл, чтобы указать расположение для файла конфигурации, отличное от HTTPS. Обратите внимание, что в Lync 2013 учитываются параметры реестра Lync 2010, но куст реестра обновлен. Вы можете создать параметры реестра следующим образом: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Type (тип): DWORD</P>
> <P>Данные значения: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Тип: строка (REG_SZ)</P>
> <P>Данные значения (примеры): file://\\лспул. Corp. contoso. ком\лсфилешаре\клиентконфигфолдер\пресенце.ксмл или file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</P></LI></UL>



</div>

Локализовать свое собственное состояние присутствия, указав одну или несколько схем ИДЕНТИФИКАТОРов языков (LCID) в XML-файле конфигурации. В примере ниже показана локализация на английский (США) (1033), Норвежский (букмол, 1044), французский (Франция) (1036) и на турецком (1055). Список LCID можно найти в <http://go.microsoft.com/fwlink/p/?linkid=157331>разделе Коды языков, назначенные корпорацией Майкрософт.

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Добавление настраиваемых состояний присутствия в Lync 2013

1.  Создайте XML-файл конфигурации, в котором используется формат следующего примера:
    
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

2.  Сохраните файл конфигурации XML на веб-сервере с включенным HTTPS. В этом примере файл имеет имя presence. XML и сохранен в указанном расположении https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

4.  В командной консоли Lync Server укажите расположение XML-файла конфигурации, выполнив команду, подобную следующей:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  С помощью командлета **Grant-CSClientPolicy** можно назначить пользователям новую политику.

Подробные сведения можно найти в разделе [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) в документации по среде управления Lync Server.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>По умолчанию Lync Server 2013&nbsp;обновляет политики клиентов и параметры каждые три часа.</P>
> <LI>
> <P>Если вы хотите продолжить использовать параметры групповой политики из предыдущих выпусков, например Кустомстатеурл, Lync 2013 будет распознавать параметры, если они находятся в новом кусте реестра (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync). Тем не менее, приоритетом обладают серверные политики на стороне сервера.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

