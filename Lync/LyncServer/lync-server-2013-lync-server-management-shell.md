---
title: 'Lync Server 2013: Командная консоль Lync Server Management Shell'
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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>командная консоль Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2017-09-20_

<div>


> [!NOTE]  
> Справочник по командлетам Skype для бизнеса перенесен на веб-сайт docs.microsoft.com. По представленным ниже ссылкам вы можете перейти на новую страницу портала docs.microsoft.com. Теперь весь контент предлагается с открытым исходным кодом и доступен в сообществе GitHub. Хотите принять участие в работе с ним? Ознакомьтесь с ФАЙЛОМ README в репозитории здесь:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 представил обширный набор новых и улучшенных функций по сравнению с тем, что было доступно в Microsoft Office Communications Server 2007 R2. Одним из улучшений является способ управления реализацией. Например, новый пользовательский интерфейс, называемый панелью управления Lync Server, — это большая смена, с которой работают другие люди с помощью консоли управления (Майкрософт). Другим серьезным улучшением управления является включение Windows PowerShell.

Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки. Она включает среду командной строки, команды для определенного продукта и полный язык сценариев. Windows PowerShell впервые была представлена в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и была включена в интерфейс командной строки для управляемости сервера Microsoft Exchange Server 2007. С этого момента она продолжает расти, и она была включена в большинство серверных продуктов Майкрософт, последние из которых представляют собой Microsoft Lync Server 2013. В Lync Server 2010 появились командлеты 550 для определенного продукта, которые можно использовать для управления всеми аспектами развертывания.

В следующих разделах представлен список командлетов и их описание. Эта информация также доступна напрямую из командной строки. Просто введите следующую команду в командной строке оболочки Lync Server Management Shell:

    Get-Help <cmdlet name> -Full

Например, чтобы получить справку по командлету **New-CsVoicePolicy** из командной строки, введите следующую команду:

    Get-Help New-CsVoicePolicy -Full

Что нужно знать о Windows PowerShell в Lync Server 2013:

  - Чтобы запустить командлеты Lync Server, откройте консоль управления Lync Server.
    
    <div>
    

    > [!WARNING]  
    > Если вы открыли окно Windows PowerShell, а не консоль управления Lync Server, по умолчанию вы не сможете запускать командлеты Lync Server. Чтобы выполнить командлеты Lync Server из Windows PowerShell, сначала введите следующую команду в командной строке Windows PowerShell:<BR>Импорт-модуль Lync

    
    </div>

  - Оболочка Lync Server Management Shell автоматически устанавливается на каждый сервер переднего плана Lync Server Enterprise Edition или Standard Edition Server.

  - Новые и обновленные сведения, примеры сценариев и Справка по началу работы с Windows PowerShell и Microsoft Lync Server 2013 доступны в блоге [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)Lync Server Windows PowerShell.

</div>

<span> </span>

</div>

</div>

</div>

