---
title: 'Lync Server 2013: Настройка ЦС предприятия для проверки подлинности с помощью смарт-карты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfbbb7a7f7787ab5490db1542c4435368a84ca0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532566"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="3e06a-102">Настройка ЦС предприятия для проверки подлинности с помощью смарт-карты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e06a-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e06a-103">_**Последнее изменение темы:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="3e06a-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="3e06a-104">В следующем разделе описывается настройка корневого центра сертификации предприятия (CA) для поддержки проверки подлинности с помощью смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="3e06a-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="3e06a-105">Сведения о том, как установить корневой центр сертификации предприятия, можно найти в статье Установка корневого центра сертификации предприятия по адресу [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .</span><span class="sxs-lookup"><span data-stu-id="3e06a-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="3e06a-106">Настройка корневого центра сертификации предприятия для поддержки проверки подлинности с помощью смарт-карты</span><span class="sxs-lookup"><span data-stu-id="3e06a-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="3e06a-107">Ниже описана процедура настройки корневого центра сертификации предприятия для поддержки проверки подлинности с помощью смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="3e06a-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="3e06a-108">Войдите на компьютер с центром сертификации предприятия с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="3e06a-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="3e06a-109">Запустите System Manager и убедитесь, что установлена роль веб-регистрации центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="3e06a-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="3e06a-110">В меню **Администрирование** откройте консоль управления **центра сертификации** .</span><span class="sxs-lookup"><span data-stu-id="3e06a-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="3e06a-111">В области навигации разверните узел **центр сертификации**.</span><span class="sxs-lookup"><span data-stu-id="3e06a-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="3e06a-112">Щелкните правой кнопкой мыши пункт **шаблоны сертификатов**, выберите пункт **создать**, а затем выберите **шаблон сертификата для выдача**.</span><span class="sxs-lookup"><span data-stu-id="3e06a-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="3e06a-113">Выберите **Агент регистрации**, **пользователь со смарт-картой**и вход с помощью смарт- **карты**.</span><span class="sxs-lookup"><span data-stu-id="3e06a-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="3e06a-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3e06a-114">Click **OK**.</span></span>

8.  <span data-ttu-id="3e06a-115">Щелкните правой кнопкой мыши пункт **шаблоны сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="3e06a-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="3e06a-116">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="3e06a-116">Select **Manage**.</span></span>

10. <span data-ttu-id="3e06a-117">Откройте свойства шаблона "пользователь смарт-карты".</span><span class="sxs-lookup"><span data-stu-id="3e06a-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="3e06a-118">Перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="3e06a-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="3e06a-119">Измените разрешения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3e06a-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="3e06a-120">Добавление отдельных учетных записей пользователей AD с разрешениями на чтение и регистрацию (Allow) или</span><span class="sxs-lookup"><span data-stu-id="3e06a-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="3e06a-121">Добавьте группу безопасности, содержащую пользователей смарт-карт с разрешениями на чтение и регистрацию (Allow), или</span><span class="sxs-lookup"><span data-stu-id="3e06a-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="3e06a-122">Добавление группы "Пользователи домена" с разрешениями на чтение и регистрацию (разрешить)</span><span class="sxs-lookup"><span data-stu-id="3e06a-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

