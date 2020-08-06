---
title: RBS (Armazenamento de Blobs Remoto) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Remote Blob Store (RBS) [SQL Server]
- RBS (Remote Blob Store) [SQL Server]
ms.assetid: 31c947cf-53e9-4ff4-939b-4c1d034ea5b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f3425474ec3b9013355536424ffcf55d9426b9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678800"
---
# <a name="remote-blob-store-rbs-sql-server"></a><span data-ttu-id="dc86b-102">RBS (Armazenamento de Blob Remoto) [SQL Server]</span><span class="sxs-lookup"><span data-stu-id="dc86b-102">Remote Blob Store (RBS) (SQL Server)</span></span>
  <span data-ttu-id="dc86b-103">O[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Remote BLOB Store (RBS) é um componente complementar opcional que permite aos administradores de bancos de dados armazenar objetos binários grandes em soluções de armazenamento de mercadorias, e não diretamente no servidor de banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="dc86b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Remote BLOB Store (RBS) is an optional add-on component that lets database administrators store binary large objects in commodity storage solutions instead of directly on the main database server.</span></span>  
  
 <span data-ttu-id="dc86b-104">O RBS está incluído na mídia de instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , mas não é instalado pelo programa de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc86b-104">RBS is included on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
 <span data-ttu-id="dc86b-105">Para mais informações sobre RBS, consulte [RBS Resources](#rbsresources) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="dc86b-105">For more information about RBS, see [RBS Resources](#rbsresources) in this topic.</span></span>  
  
## <a name="benefits-of-rbs"></a><span data-ttu-id="dc86b-106">Benefícios do RBS</span><span class="sxs-lookup"><span data-stu-id="dc86b-106">Benefits of RBS</span></span>  
 <span data-ttu-id="dc86b-107">O RBS oferece os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="dc86b-107">RBS provides the following benefits:</span></span>  
  
### <a name="optimized-database-storage-and-performance"></a><span data-ttu-id="dc86b-108">Armazenamento e desempenho de banco de dados otimizados</span><span class="sxs-lookup"><span data-stu-id="dc86b-108">Optimized database storage and performance</span></span>  
 <span data-ttu-id="dc86b-109">O armazenamento de BLOBs no banco de dados pode consumir muito espaço em arquivo e envolver recursos caros de servidor.</span><span class="sxs-lookup"><span data-stu-id="dc86b-109">Storing BLOBs in the database can consume large amounts of file space and expensive server resources.</span></span> <span data-ttu-id="dc86b-110">O RBS transfere os BLOBs com eficácia para uma solução de armazenamento dedicada de sua preferência e armazena as referências a eles no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dc86b-110">RBS efficiently transfers the BLOBs to a dedicated storage solution of your choosing, and stores references to them in the database.</span></span> <span data-ttu-id="dc86b-111">Isso libera armazenamento do servidor para dados estruturados e também libera recursos do servidor para operações de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dc86b-111">This frees server storage for structured data, and frees server resources for database operations.</span></span>  
  
### <a name="efficient-management-of-blobs"></a><span data-ttu-id="dc86b-112">Gerenciamento eficaz de BLOBs</span><span class="sxs-lookup"><span data-stu-id="dc86b-112">Efficient management of BLOBs</span></span>  
 <span data-ttu-id="dc86b-113">Vários recursos do RBS oferecem suporte ao gerenciamento conveniente de BLOBs armazenados:</span><span class="sxs-lookup"><span data-stu-id="dc86b-113">Several RBS features support the convenient management of stored BLOBs:</span></span>  
  
-   <span data-ttu-id="dc86b-114">BLOBS são gerenciados com transações ACID (atomicidade, consistência, isolamento e durabilidade).</span><span class="sxs-lookup"><span data-stu-id="dc86b-114">BLOBS are managed with ACID (atomic consistency isolation durable) transactions.</span></span>  
  
-   <span data-ttu-id="dc86b-115">BLOBs são organizados em coleções.</span><span class="sxs-lookup"><span data-stu-id="dc86b-115">BLOBs are organized into collections.</span></span>  
  
-   <span data-ttu-id="dc86b-116">São incluídas a coleta de lixo, a verificação de consistência e outras funções de manutenção.</span><span class="sxs-lookup"><span data-stu-id="dc86b-116">Garbage collection, consistency checking, and other maintenance functions are included.</span></span>  
  
### <a name="standardized-api"></a><span data-ttu-id="dc86b-117">API padronizada</span><span class="sxs-lookup"><span data-stu-id="dc86b-117">Standardized API</span></span>  
 <span data-ttu-id="dc86b-118">O RBS define um conjunto de APIs que fornecem um modelo de programação padronizado para que os aplicativos acessem e modifiquem qualquer repositório de BLOB.</span><span class="sxs-lookup"><span data-stu-id="dc86b-118">RBS defines a set of APIs that provide a standardized programming model for applications to access and modify any BLOB store.</span></span> <span data-ttu-id="dc86b-119">Cada repositório de BLOB pode especificar sua própria biblioteca de provedores, que se conecta à biblioteca cliente RBS e especifica como os BLOBs são armazenados e acessados.</span><span class="sxs-lookup"><span data-stu-id="dc86b-119">Each BLOB store can specify its own provider library, which plugs into the RBS client library and specifies how BLOBs are stored and accessed.</span></span>  
  
 <span data-ttu-id="dc86b-120">Vários fornecedores de solução de armazenamento de terceiros desenvolveram provedores RBS que estão em conformidade com estas APIs padrão e oferecem suporte ao armazenamento de BLOB em várias plataformas de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="dc86b-120">A number of third-party storage solution vendors have developed RBS providers that conform to these standard APIs and support BLOB storage on various storage platforms.</span></span>  
  
## <a name="rbs-requirements"></a><span data-ttu-id="dc86b-121">Requisitos de RBS</span><span class="sxs-lookup"><span data-stu-id="dc86b-121">RBS Requirements</span></span>  
 <span data-ttu-id="dc86b-122">O RBS requer o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise para o servidor de banco de dados principal no qual os metadados de BLOB são armazenados.</span><span class="sxs-lookup"><span data-stu-id="dc86b-122">RBS requires [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise for the main database server in which the BLOB metadata is stored.</span></span> <span data-ttu-id="dc86b-123">Porém, se você usar o provedor FILESTREAM fornecido, poderá armazenar os próprios BLOBs no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.</span><span class="sxs-lookup"><span data-stu-id="dc86b-123">However, if you use the supplied FILESTREAM provider, you can store the BLOBs themselves on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.</span></span>  
  
 <span data-ttu-id="dc86b-124">O RBS inclui um provedor FILESTREAM que permite usar o RBS para armazenar BLOBs em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc86b-124">RBS includes a FILESTREAM provider that lets you use RBS to store BLOBs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dc86b-125">Caso deseje usar o RBS para armazenar BLOBs em uma solução de armazenamento diferente, utilize um provedor RBS de terceiros desenvolvido para essa solução de armazenamento ou desenvolva um provedor RBS personalizado usando a API do RBS.</span><span class="sxs-lookup"><span data-stu-id="dc86b-125">If you want use RBS to store BLOBs in a different storage solution, you have to use a third party RBS provider developed for that storage solution, or develop a custom RBS provider using the RBS API.</span></span> <span data-ttu-id="dc86b-126">Um provedor de exemplo que armazena BLOBs no sistema de arquivos NTFS está disponível como um recurso de aprendizagem em [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190).</span><span class="sxs-lookup"><span data-stu-id="dc86b-126">A sample provider that stores BLOBs in the NTFS file system is available as a learning resource on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190).</span></span>  
  
## <a name="rbs-security"></a><span data-ttu-id="dc86b-127">Segurança do RBS</span><span class="sxs-lookup"><span data-stu-id="dc86b-127">RBS Security</span></span>  
 <span data-ttu-id="dc86b-128">Quando você usar um provedor personalizado para armazenar BLOBs fora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], talvez eles estejam disponíveis para outros processos que ignorem o sistema de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc86b-128">When you use a custom provider to store BLOBs outside of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they may be available to other processes that bypass the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security system.</span></span> <span data-ttu-id="dc86b-129">Proteja os BLOBs armazenados com permissões e opções de criptografia apropriadas para a mídia de armazenamento usada pelo provedor personalizado.</span><span class="sxs-lookup"><span data-stu-id="dc86b-129">Make sure that you protect the stored BLOBs with permissions and encryption options that are appropriate to the storage medium used by the custom provider.</span></span>  
  
##  <a name="rbs-resources"></a><a name="rbsresources"></a><span data-ttu-id="dc86b-130">Recursos do RBS</span><span class="sxs-lookup"><span data-stu-id="dc86b-130">RBS Resources</span></span>  
 <span data-ttu-id="dc86b-131">**Documentação do RBS**</span><span class="sxs-lookup"><span data-stu-id="dc86b-131">**RBS documentation**</span></span>  
 <span data-ttu-id="dc86b-132">A documentação do RBS está incluída no pacote do Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="dc86b-132">The RBS documentation is included in the Windows installer package.</span></span> <span data-ttu-id="dc86b-133">Se você desejar revisar a documentação do RBS sem instalar o RBS, poderá exibir a versão [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] da documentação [online na Biblioteca do MSDN](https://go.microsoft.com/fwlink/?LinkId=210192).</span><span class="sxs-lookup"><span data-stu-id="dc86b-133">If you want to review the RBS documentation without installing RBS, you can view the [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] version of the documentation [online in the MSDN Library](https://go.microsoft.com/fwlink/?LinkId=210192).</span></span>  
  
 <span data-ttu-id="dc86b-134">**White paper do RBS**</span><span class="sxs-lookup"><span data-stu-id="dc86b-134">**RBS white paper**</span></span>  
 <span data-ttu-id="dc86b-135">O white paper "[Remote BLOB Storage](https://go.microsoft.com/fwlink/?LinkId=210422)", que está disponível para download como um documento do Microsoft Word, fornece informações detalhadas sobre como instalar e configurar o RBS.</span><span class="sxs-lookup"><span data-stu-id="dc86b-135">The white paper "[Remote BLOB Storage](https://go.microsoft.com/fwlink/?LinkId=210422)", which is available for download as a Microsoft Word document, provides detailed information about installing and configuring RBS.</span></span>  
  
 <span data-ttu-id="dc86b-136">**Exemplos do RBS**</span><span class="sxs-lookup"><span data-stu-id="dc86b-136">**RBS samples**</span></span>  
 <span data-ttu-id="dc86b-137">Os exemplos do RBS disponíveis em [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190) demonstram como desenvolver um aplicativo RBS, e como desenvolver e instalar um provedor RBS personalizado.</span><span class="sxs-lookup"><span data-stu-id="dc86b-137">The RBS samples available on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190) demonstrate how to develop an RBS application, and how to develop and install a custom RBS provider.</span></span>  
  
 <span data-ttu-id="dc86b-138">**Blog do RBS**</span><span class="sxs-lookup"><span data-stu-id="dc86b-138">**RBS blog**</span></span>  
 <span data-ttu-id="dc86b-139">O [blog do RBS](https://go.microsoft.com/fwlink/?LinkId=210315) fornece informações adicionais para ajudá-lo a compreender, implantar e manter o RBS.</span><span class="sxs-lookup"><span data-stu-id="dc86b-139">The [RBS blog](https://go.microsoft.com/fwlink/?LinkId=210315) provides additional information to help you understand, deploy, and maintain RBS.</span></span>  
  
  
