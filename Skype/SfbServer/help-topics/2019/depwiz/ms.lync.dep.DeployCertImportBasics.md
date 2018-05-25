---
title: Импорт сертификата (введение)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: Чтобы импортировать сертификат, необходимо указать путь к файлу сертификата. В текстовом поле Выбор сертификата файла можно либо введите полный путь и имя файла или нажмите кнопку Обзор и перейдите в расположение путь и имя файла (как правило, .p7b, PFX-файл или CER-файл).
ms.openlocfilehash: f83f42bbd8515ae20510d8253b560a93070e9ed6
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="import-certificate-intro"></a><span data-ttu-id="d9eef-104">Импорт сертификата (введение)</span><span class="sxs-lookup"><span data-stu-id="d9eef-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="d9eef-105">Чтобы импортировать сертификат, необходимо указать путь к файлу сертификата.</span><span class="sxs-lookup"><span data-stu-id="d9eef-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="d9eef-106">В поле **Выбор сертификата файла** можно либо введите полный путь и имя файла или нажмите кнопку **Обзор** и перейдите в расположение путь и имя файла (как правило, .p7b, PFX-файл или CER-файл).</span><span class="sxs-lookup"><span data-stu-id="d9eef-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="d9eef-107">Если сертификат содержит закрытый ключ, установите флажок, **файл сертификата содержит закрытый ключ сертификата**.</span><span class="sxs-lookup"><span data-stu-id="d9eef-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="d9eef-108">Если этот флажок установлен, ввода текста **пароля** включено.</span><span class="sxs-lookup"><span data-stu-id="d9eef-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="d9eef-109">Если у вас есть сертификат с закрытым ключом, связанные с ним, пароль обычно размещается на закрытый ключ при создании сертификата.</span><span class="sxs-lookup"><span data-stu-id="d9eef-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="d9eef-110">Введите пароль для закрытого ключа, чтобы разрешить сертификат и закрытый ключ к импорту в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d9eef-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="d9eef-111">Когда вы предоставили сведения для путь к файлу сертификата, а при необходимости и пароль для закрытого ключа, при необходимости, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d9eef-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d9eef-112">Если вы не знаете пароль для закрытого ключа, импорт не выполнится.</span><span class="sxs-lookup"><span data-stu-id="d9eef-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

