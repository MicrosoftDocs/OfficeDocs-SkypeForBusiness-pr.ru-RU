---
title: 'Lync Server 2013: Командная консоль Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc4ab6a9c32a8b060308526fcdb1f1da403a9e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-09-20_

<div>


> [!NOTE]  
> Ссылка на командлет Skype для бизнеса перемещена в docs.microsoft.com. Перейдя по приведенным ниже ссылкам, вы перейдете на новую страницу docs.microsoft.com. Теперь контент открыт в исходном и доступном для участия в сообществах с помощью GitHub. Интересуетесь участниками? Ознакомьтесь со статьей README в репозитории здесь:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

В Microsoft Lync Server 2010 появился большой набор новых и улучшенных функций по сравнению с тем, что было доступно в Microsoft Office Communications Server 2007 R2. Одним из улучшений является способ управления реализацией. Например, существует новый пользовательский интерфейс, называемый панелью управления Lync Server, который представляет большой сдвиг от большинства людей, используемых в консоли управления (MMC). Другим важным улучшением управления является включение Windows PowerShell.

Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки. Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов. Windows PowerShell впервые появился в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и был включен в качестве интерфейса командной строки для управления Microsoft Exchange Server 2007. С этого точки он продолжает расти и включен в большинство серверных продуктов корпорации Майкрософт, самые последние из них — Microsoft Lync Server 2013. Lync Server 2010 представил более 550 командлетов для конкретных продуктов, которые можно использовать для управления каждым аспектом развертывания.

В следующих разделах представлен список командлетов и их описание. Эта информация также доступна напрямую из командной строки. Просто введите в командной строке Командная консоль Lync Server следующую команду:

    Get-Help <cmdlet name> -Full

Например, чтобы получить справку по командлету **New-CsVoicePolicy** из командной строки, введите следующую команду:

    Get-Help New-CsVoicePolicy -Full

Что нужно знать о Windows PowerShell в Lync Server 2013:

  - Чтобы запустить командлеты Lync Server, откройте консоль управления Lync Server.
    
    <div>
    

    > [!WARNING]  
    > Если открыть окно Windows PowerShell, а не командную консоль Lync Server, по умолчанию командлеты Lync Server не будут доступны. Чтобы запустить командлеты Lync Server в Windows PowerShell, сначала введите следующую команду в командной строку Windows PowerShell:<BR>Import-Module Lync

    
    </div>

  - Консоль управления Lync Server автоматически устанавливается на каждом сервере переднего плана Lync Server Enterprise Edition или на сервере Standard Edition.

  - Новые и обновленные сведения, примеры сценариев и Справка по началу работы и дополнительные сведения о командлетах Windows PowerShell и Microsoft Lync Server 2013 доступны в блоге [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)Lync Server Windows PowerShell.

</div>

<span> </span>

</div>

</div>

</div>

