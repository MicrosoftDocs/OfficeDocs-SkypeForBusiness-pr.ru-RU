---
title: Импорт сертификата (введение)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: Чтобы импортировать сертификат, необходимо указать путь к файлу сертификата. В поле Выбрать файл сертификата можно либо ввести полный путь и имя файла, либо нажать кнопку Обзор и выбрать путь и имя файла (обычно это файл с расширением .p7b, .pfx или .cer).
ms.openlocfilehash: 2ca89291376c488426001e1ff42c4925da58a3e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827289"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="5edda-104">Импорт сертификата (введение)</span><span class="sxs-lookup"><span data-stu-id="5edda-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="5edda-p102">Чтобы импортировать сертификат, необходимо указать путь к файлу сертификата. В поле **Выбрать файл сертификата** можно либо ввести полный путь и имя файла, либо нажать кнопку **Обзор** и выбрать путь и имя файла (обычно это файл с расширением .p7b, .pfx или .cer).</span><span class="sxs-lookup"><span data-stu-id="5edda-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="5edda-107">Если сертификат содержит закрытый ключ, выберите в файле сертификата его **закрытый ключ.**</span><span class="sxs-lookup"><span data-stu-id="5edda-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="5edda-108">Когда этот флажок установлен, активируется поле ввода **Пароль**.</span><span class="sxs-lookup"><span data-stu-id="5edda-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="5edda-109">Если с сертификатом связан закрытый ключ, то при создании сертификата пароль обычно помещается в закрытом ключе.</span><span class="sxs-lookup"><span data-stu-id="5edda-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="5edda-110">Вы должны ввести пароль для закрытого ключа, чтобы импортировать сертификат и закрытый ключ в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5edda-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="5edda-111">Указав путь к файлу сертификата и при необходимости пароль закрытого ключа, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5edda-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5edda-112">Если вы не знаете пароль для закрытого ключа, импорт не выполнится.</span><span class="sxs-lookup"><span data-stu-id="5edda-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

