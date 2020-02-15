---
title: 'Lync Server 2013: Настройка настраиваемых состояний присутствия'
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
ms.openlocfilehash: 75e2e47af4951e98f21ea6b26572d39b5eebcb8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Настройка настраиваемых состояний присутствия в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-10_

Чтобы определить настраиваемые состояния присутствия в Lync 2013, создайте файл настраиваемой конфигурации сведений о присутствии XML, а затем укажите его расположение с помощью командлетов командной консоли Lync Server **New-CSClientPolicy** или **Set-CSClientPolicy** с параметром кустомстатеурл.

Файлы конфигурации имеют следующие свойства:

  - Настраиваемые состояния присутствия можно настроить с индикаторами присутствия "доступно", "занято" и "не беспокоить".

  - Атрибут Availability определяет, какой индикатор присутствия связан с текстом состояния настраиваемого состояния. В примере ниже в этом разделе текст состояния, работающий с домашней страницы, отображается справа от индикатора присутствия зеленого (доступного) индикатора присутствия.

  - Максимальная длина текста состояния — 64 символов.

  - Можно добавить не более четырех настраиваемых состояний присутствия.

  - Параметр Кустомстатеурл указывает расположение файла конфигурации. В Lync 2013 режим высокой безопасности SIP включен по умолчанию, поэтому необходимо хранить пользовательский файл конфигурации присутствия на веб-сервере с включенным протоколом HTTPS. В противном случае Lync 2013 клиенты не смогут подключаться к нему. Например, допустимым адресом является `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<div>


> [!NOTE]  
> Хотя это не рекомендуется в рабочей среде, вы можете протестировать файл конфигурации, расположенный на общем файловом ресурсе, с помощью параметра реестра EnableSIPHighSecurityMode, чтобы отключить режим высокой безопасности SIP на клиенте. Затем можно использовать параметр реестра Кустомстатеурл, чтобы указать расположение для файла конфигурации, отличное от HTTPS. Обратите внимание, что в Lync 2013 учитываются параметры реестра Lync 2010, но куст реестра обновлен. Вы создадите параметры реестра следующим образом: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Тип: DWORD</P>
> <P>Данные значения: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Тип: строка (REG_SZ)</P>
> <P>Данные о значении (примеры)\\: file://лспул. Corp. contoso. ком\лсфилешаре\клиентконфигфолдер\пресенце.ксмл или file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</P></LI></UL>



</div>

Локализовать пользовательское состояние присутствия, указав одну или несколько схем ИДЕНТИФИКАТОРов языковых стандартов (LCID) в XML-файле конфигурации. В примере далее в этом разделе показано локализация на английский (США), Норвежский (1033), Норвежский (1044), французский (США), французский (1055) (1036) и Турецкий (). Список LCID можно узнать в статье Языковые идентификаторы, назначенные корпорацией <http://go.microsoft.com/fwlink/p/?linkid=157331>Майкрософт по адресу.

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

2.  Сохраните XML-файл конфигурации на веб-сервере с включенной поддержкой протокола HTTPS. В этом примере файл имеет имя presence. XML и сохраняется в указанном расположении https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

4.  В командной консоли Lync Server определите расположение XML-файла конфигурации с помощью команды, аналогичной следующей:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Используйте командлет **Grant – CSClientPolicy** для назначения этой новой политики пользователям.

Дополнительные сведения см. в статье [New/CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и [Grant – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) в документации по консоли управления Lync Server.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>По умолчанию Lync Server 2013&nbsp;обновляет политики клиентов и параметры каждые три часа.</P>
> <LI>
> <P>Если вы хотите продолжить использование параметров групповой политики из предыдущих выпусков, таких как Кустомстатеурл, то Lync 2013 будет распознавать параметры, если они находятся в новом кусте реестра (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync). Тем не менее, приоритет имеют серверные политики клиентов.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

