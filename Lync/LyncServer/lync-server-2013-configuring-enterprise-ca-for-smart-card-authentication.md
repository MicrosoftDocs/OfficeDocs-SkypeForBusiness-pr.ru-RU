---
title: 'Lync Server 2013: Настройка ЦС предприятия для проверки подлинности с помощью смарт-карты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="3d1f6-102">Настройка ЦС предприятия для проверки подлинности с помощью смарт-карты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1f6-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d1f6-103">_**Тема последнего изменения:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="3d1f6-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="3d1f6-104">В следующем разделе описано, как настроить корневой центр сертификации (ЦС) предприятия для поддержки проверки подлинности с помощью смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="3d1f6-105">Сведения о том, как установить корневой центр сертификации предприятия, можно найти в разделе Установка корневого [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)ЦС предприятия по адресу.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="3d1f6-106">Настройка корневого центра сертификации предприятия для поддержки проверки подлинности с помощью смарт-карты</span><span class="sxs-lookup"><span data-stu-id="3d1f6-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="3d1f6-107">Ниже описан порядок действий по настройке корневого ЦС предприятия для проверки подлинности с помощью смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="3d1f6-108">Войдите на компьютер ЦС предприятия с учетной записью администратора домена.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="3d1f6-109">Запустите приложение System Manager и убедитесь в том, что установлена роль регистрации сертификатов через Интернет.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="3d1f6-110">В меню **Администрирование** откройте консоль управления **Центр сертификации**.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="3d1f6-111">В области навигации разверните элемент **Центр сертификации**.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="3d1f6-112">Щелкните правой кнопкой **Шаблоны сертификатов** и выберите **Создать**, затем **Выдаваемый шаблон сертификата**.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="3d1f6-113">Выберите **Агент подачи заявок**, **Пользователь со смарт-картой** и **Вход со смарт-картой**.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="3d1f6-114">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-114">Click **OK**.</span></span>

8.  <span data-ttu-id="3d1f6-115">Щелкните **Шаблоны сертификатов** правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="3d1f6-116">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-116">Select **Manage**.</span></span>

10. <span data-ttu-id="3d1f6-117">Откройте свойства шаблона пользователя смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="3d1f6-118">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="3d1f6-119">Задайте указанные ниже разрешения.</span><span class="sxs-lookup"><span data-stu-id="3d1f6-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="3d1f6-120">Добавьте учетные записи отдельных пользователей Active Directory с разрешениями на чтение и подачу заявок (разрешить).</span><span class="sxs-lookup"><span data-stu-id="3d1f6-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="3d1f6-121">Добавьте группу безопасности с пользователями смарт-карт, обладающую разрешениями на чтение и подачу заявок (разрешить).</span><span class="sxs-lookup"><span data-stu-id="3d1f6-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="3d1f6-122">Добавьте группу пользователей домена с разрешениями на чтение и подачу заявок (разрешить).</span><span class="sxs-lookup"><span data-stu-id="3d1f6-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

