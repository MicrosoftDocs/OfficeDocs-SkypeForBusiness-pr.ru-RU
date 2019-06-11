---
title: 'Lync Server 2013: Общие сведения о гибридной среде Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Общие сведения о гибридной среде Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-28_

Гибридная Среда Lync Server 2013 имеет отношение к развертыванию, в котором некоторые пользователи находятся на локальном сервере Lync Server 2013 и других пользователях, подключенных к Lync Online, но пользователи имеют доступ к тому же домену, например user@contoso.com.

<div>

## <a name="about-this-guide"></a>Сведения об этом руководстве

В этом руководстве описаны задачи, необходимые для настройки среды Lync Server 2013 для взаимодействия с Lync Online, а также перемещения пользователей из локального развертывания для использования Lync Online.

</div>

<div>

## <a name="prerequisites"></a>Необходимые компоненты

Для выполнения задач по настройке гибридного развертывания на компьютере должны быть установлены следующие приложения и служебные программы. Установщики для этих файлов будут включены в установочный носитель, указанный для развертывания, а также ссылки, приведенные в следующем списке.

  - [Службы федерации Active Directory (AD FS) 2,0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Средство синхронизации каталогов Microsoft 9,1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Установка Windows PowerShell для единого входа с помощью AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Помощник по входу в Microsoft Online Services (мсоидкли-7.0. msi) включен в настройку рабочего стола для Office 365, которая может быть получена со страницы загрузки, связанной с порталом администрирования Office 365.

</div>

<div>

## <a name="administrator-credentials"></a>Учетные данные администратора

Когда вам будет предложено ввести учетные данные администратора, введите имя пользователя и пароль для учетной записи администратора в клиенте Office 365. Эти учетные данные также будут использоваться при настройке служб федерации Active Directory (AD FS) 2,0, синхронизации каталогов, единого входа, Федерации и перемещения пользователей на Lync Online.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Подключение к Lync Online PowerShell

Администраторы теперь могут использовать Windows PowerShell для управления Lync Online и их учетными записями пользователей Lync Online. Для этого сначала необходимо скачать и установить модуль соединительной линии Lync Online из центра загрузки Майкрософт (http://go.microsoft.com/fwlink/?LinkId=294688). Дополнительные сведения о загрузке, установке и использовании модуля соединительной линии Lync Online и подробные сведения об использовании Windows PowerShell для управления Lync Online можно найти [в разделе Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

