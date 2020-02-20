---
title: 'Lync Server 2013: Настройка Windows 8 для виртуальных смарт-карт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fa0be32f5a2c2a0af0b63dadddda3038675adf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="9cfb0-102">Настройка Windows 8 для использования виртуальных смарт-карт с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfb0-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cfb0-103">_**Последнее изменение темы:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="9cfb0-104">Один фактор, который необходимо учитывать при развертывании двухфакторной проверки подлинности и технологии смарт-карт, — это стоимость реализации.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="9cfb0-105">Windows 8 предоставляет ряд новых возможностей обеспечения безопасности, а одна из наиболее интересных новых функций поддерживает виртуальные смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="9cfb0-106">Для компьютеров с микросхемами доверенного платформенного модуля (TPM), соответствующих спецификации версии 1,2, организации могут использовать преимущества входа с помощью смарт-карты, не внося дополнительных инвестиций в оборудование.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="9cfb0-107">Для получения дополнительных сведений обратитесь к разделу Использование виртуальной смарт-карты [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365)в Windows 8 по адресу.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-107">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="9cfb0-108">Настройка Windows 8 для виртуальных смарт-карт</span><span class="sxs-lookup"><span data-stu-id="9cfb0-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="9cfb0-109">Войдите на компьютер с Windows 8, используя учетные данные пользователя с включенной поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="9cfb0-110">На начальном экране Windows 8 переместите курсор в правый нижний угол экрана.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="9cfb0-111">Выберите параметр **Поиск** , а затем выполните поиск в **командной строки**.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="9cfb0-112">Щелкните правой кнопкой мыши пункт **Командная строка**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="9cfb0-113">Откройте консоль управления доверенным платформенным модулем (TPM), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="9cfb0-114">В консоли управления TPM убедитесь, что в качестве версии спецификации доверенного платформенного модуля задано по крайней мере 1,2</span><span class="sxs-lookup"><span data-stu-id="9cfb0-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9cfb0-115">Если появится диалоговое окно с сообщением о том, что не удается найти совместимый доверенный платформенный модуль, убедитесь, что на компьютере установлен совместимый модуль TPM и он включен в BIOS системы.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="9cfb0-116">Закройте консоль управления TPM</span><span class="sxs-lookup"><span data-stu-id="9cfb0-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="9cfb0-117">В командной строки создайте новую виртуальную смарт-карту с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9cfb0-118">Чтобы задать пользовательское значение ПИН-кода при создании виртуальной смарт-карты, используйте вместо этого запрос/ПИН.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="9cfb0-119">В командной строки откройте консоль "Управление компьютером", выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="9cfb0-120">В консоли Управление компьютером выберите **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="9cfb0-121">Разверните элемент **устройства чтения смарт-карт**.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="9cfb0-122">Убедитесь, что новое устройство чтения виртуальной смарт-карт успешно создано.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

