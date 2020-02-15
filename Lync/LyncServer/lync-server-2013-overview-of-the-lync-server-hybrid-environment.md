---
title: 'Lync Server 2013: обзор гибридной среды Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32132faee3b52140d20a7f01e6a0bad0e88c620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Обзор гибридной среды Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-28_

Гибридная Среда Lync Server 2013 относится к развертыванию, в котором есть некоторые пользователи, размещенные на локальном сервере Lync Server 2013 и другие пользователи, размещенные в Lync Online, но пользователи используют один и тот же домен, например user@contoso.com.

<div>

## <a name="about-this-guide"></a>Сведения о данном руководстве

В этом руководстве описываются задачи, необходимые для настройки среды Lync Server 2013 для взаимодействия с Lync Online, а также перемещения пользователей из локального развертывания для использования Lync Online.

</div>

<div>

## <a name="prerequisites"></a>Необходимые компоненты

Для выполнения задач, необходимых для настройки развертывания гибридной среды, необходимо установить следующие приложения и служебные программы. Установщики для этих файлов находятся на установочном носителе, предоставленном вам для развертывания, а также по ссылкам в следующем списке.

  - [Службы федерации Active Directory (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Средство синхронизации каталогов (Майкрософт) 9,1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Установка Windows PowerShell для единого входа с помощью AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Помощник по входу в Microsoft Online Services (мсоидкли-7.0. msi) включен в настройку рабочего стола для Office 365, которую можно получить на странице Загружаемые файлы, связанную с порталом администрирования Office 365.

</div>

<div>

## <a name="administrator-credentials"></a>Учетные данные администратора

Когда вам будет предложено ввести учетные данные администратора, укажите имя пользователя и пароль учетной записи администратора для клиента Office 365. Эти учетные данные также будут использоваться при настройке служб федерации Active Directory (AD FS) 2,0, синхронизации каталогов, единого входа, Федерации и перемещения пользователей в Lync Online.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Подключение к Lync Online PowerShell

Теперь администраторы могут использовать Windows PowerShell для управления Lync Online и учетными записями пользователей Lync Online. Для этого необходимо сначала скачать и установить модуль соединителя Lync Online в центре загрузки Майкрософт (http://go.microsoft.com/fwlink/?LinkId=294688). Дополнительные сведения о загрузке, установке и использовании модуля соединителя Lync Online и подробные сведения об использовании Windows PowerShell для управления Lync Online приведены в статье [Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

