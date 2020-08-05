---
title: Instalando o conector da Microsoft para 1,1 SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3bfb9023-9597-4f59-9085-4b9057e7702e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ef96f38054f04e71de72bda0bbb12f8f003ef20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573188"
---
# <a name="installing-the-microsoft-connector-for-11-sap-bw"></a><span data-ttu-id="82349-102">Instalando o Microsoft Connector para 1.1 SAP BW</span><span class="sxs-lookup"><span data-stu-id="82349-102">Installing the Microsoft Connector for 1.1 SAP BW</span></span>
  <span data-ttu-id="82349-103">Para instalar o [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW e sua documentação, baixe e execute o pacote do Windows Installer na página da Web do SQL Server Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="82349-103">To install the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW and its documentation, download and run the Windows installer package from the SQL Server Feature Pack Web page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82349-104">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="82349-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="82349-105">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="82349-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82349-106">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="82349-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="82349-107">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="82349-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="required-sap-files"></a><span data-ttu-id="82349-108">Arquivos necessários do SAP</span><span class="sxs-lookup"><span data-stu-id="82349-108">Required SAP Files</span></span>  
 <span data-ttu-id="82349-109">Para usar o [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW, não é necessário instalar o software de front-end do SAP (SAP GUI) no computador local.</span><span class="sxs-lookup"><span data-stu-id="82349-109">To use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, you do not have to install the SAP Front End software (SAP GUI) on the local computer.</span></span>  
  
 <span data-ttu-id="82349-110">No entanto, você deve copiar o arquivo do connector do SAP .NET, librfc32.dll, na subpasta do sistema na pasta Windows.</span><span class="sxs-lookup"><span data-stu-id="82349-110">However you must copy the SAP .NET connector file, librfc32.dll, into the system subfolder in the Windows folder.</span></span> <span data-ttu-id="82349-111">(Normalmente, o local da pasta é **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="82349-111">(Typically, this folder location is **C:\Windows\system32**.)</span></span>  
  
## <a name="considerations-for-64-bit-computers"></a><span data-ttu-id="82349-112">Considerações para computadores de 64 bits</span><span class="sxs-lookup"><span data-stu-id="82349-112">Considerations for 64-bit Computers</span></span>  
 <span data-ttu-id="82349-113">O [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW dá suporte total à versão de 64 bits do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="82349-113">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW fully supports the 64-bit version of [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="82349-114">Em um computador de 64 bits, o [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW tem os seguintes requisitos adicionais:</span><span class="sxs-lookup"><span data-stu-id="82349-114">On a 64-bit computer, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following additional requirements:</span></span>  
  
-   <span data-ttu-id="82349-115">Para executar pacotes no modo de 64 bits em qualquer sistema operacional Windows de 64 bits, copie a versão de 64 bits do arquivo do SAP GUI, librfc32.dll, para a pasta **system32** da pasta Windows.</span><span class="sxs-lookup"><span data-stu-id="82349-115">To run packages in 64-bit mode on any 64-bit Windows operating system, copy the 64-bit version of the SAP GUI file, librfc32.dll, into the **system32** folder of the Windows folder.</span></span> <span data-ttu-id="82349-116">(Normalmente, o local do arquivo é **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="82349-116">(Typically, this file location is **C:\Windows\system32**.)</span></span>  
  
-   <span data-ttu-id="82349-117">Para executar pacotes no modo de 32 bits em qualquer sistema operacional Windows de 64 bits, copie o arquivo do SAP GUI, librfc32.dll, para a pasta **SysWow64** da pasta Windows.</span><span class="sxs-lookup"><span data-stu-id="82349-117">To run packages in 32-bit mode on any 64-bit Windows operating system, copy the SAP GUI file, librfc32.dll, into the **SysWow64** folder of the Windows folder.</span></span> <span data-ttu-id="82349-118">(Normalmente, o local da pasta é **C:\Windows\SysWow64**.)</span><span class="sxs-lookup"><span data-stu-id="82349-118">(Typically, this folder location is **C:\Windows\SysWow64**.)</span></span>  
  
  
