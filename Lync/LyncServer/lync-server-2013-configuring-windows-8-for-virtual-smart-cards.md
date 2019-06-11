---
title: 'Lync Server 2013: Настройка Windows 8 для виртуальных смарт-карт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="fe463-102">Настройка Windows 8 для использования виртуальных смарт-карт с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe463-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe463-103">_**Тема последнего изменения:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="fe463-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="fe463-104">Одним их факторов, которые следует учитывать при развертывании двухфакторной проверки подлинности и технологии смарт-карт, является его стоимость.</span><span class="sxs-lookup"><span data-stu-id="fe463-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="fe463-105">Windows 8 предлагает ряд новых возможностей обеспечения безопасности, а одна из наиболее интересных новых возможностей — поддержка виртуальных смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="fe463-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="fe463-106">Если компьютеры оборудованы микросхемами доверенного платформенного модуля (TPM), соответствующими спецификации версии 1.2, организации могут пользоваться преимуществами регистрации по смарт-картам без дополнительных капиталовложений в оборудование.</span><span class="sxs-lookup"><span data-stu-id="fe463-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="fe463-107">Дополнительные сведения можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)разделе Использование виртуальных смарт-карт в Windows 8.</span><span class="sxs-lookup"><span data-stu-id="fe463-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="fe463-108">Настройка конфигурации Windows 8 для виртуальных смарт-карт</span><span class="sxs-lookup"><span data-stu-id="fe463-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="fe463-109">Войдите в систему на компьютере с Windows 8, используя учетные данные пользователя с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="fe463-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="fe463-110">На начальном экране Windows 8 переместите курсор в нижний правый угол.</span><span class="sxs-lookup"><span data-stu-id="fe463-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="fe463-111">Выберите команду **Поиск** и найдите элемент **Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="fe463-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="fe463-112">Щелкните **Командная строка** правой кнопкой мыши, затем выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="fe463-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="fe463-113">Откройте консоль управления TPM, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe463-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="fe463-114">Убедитесь в том, что спецификация вашего TPM имеет версию 1.2 или выше.</span><span class="sxs-lookup"><span data-stu-id="fe463-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe463-115">При появлении диалогового окна с сообщением, что совместимый TPM не найден, убедитесь в том, что ваш компьютер имеет совместимый модуль TPM и что он включен в BIOS компьютера.</span><span class="sxs-lookup"><span data-stu-id="fe463-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="fe463-116">Закройте консоль управления TPM</span><span class="sxs-lookup"><span data-stu-id="fe463-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="fe463-117">Создайте новую виртуальную смарт-карту, введя в командную строку следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe463-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe463-118">Чтобы сообщить настраиваемое значение ПИН-кода, используйте ключ командной строки /pin.</span><span class="sxs-lookup"><span data-stu-id="fe463-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="fe463-119">Откройте консоль управления компьютером, введя в командную строку следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe463-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="fe463-120">В консоли управления компьютером выберите **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="fe463-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="fe463-121">Разверните элемент **Устройства чтения смарт-карт**.</span><span class="sxs-lookup"><span data-stu-id="fe463-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="fe463-122">Убедитесь в том, что создание нового устройства для чтения виртуальной смарт-карты успешно завершено.</span><span class="sxs-lookup"><span data-stu-id="fe463-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

