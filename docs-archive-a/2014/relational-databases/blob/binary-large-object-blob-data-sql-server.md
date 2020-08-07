---
title: Dados de objeto binário grande (Blob) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], design and implementation
ms.assetid: 97509274-c3f8-43e5-a37c-52f1ffe0961a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a663dedf34d75a21ee8df6b97979548c04abf7ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581974"
---
# <a name="binary-large-object-blob-data-sql-server"></a><span data-ttu-id="20661-102">Dados de objeto binário grande (Blob) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="20661-102">Binary Large Object (Blob) Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="20661-103">oferece soluções para armazenar arquivos e documentos no banco de dados ou em dispositivos de armazenamento remotos.</span><span class="sxs-lookup"><span data-stu-id="20661-103">provides solutions for storing files and documents in the database or on remote storage devices.</span></span>  
  
##  <a name="in-this-section"></a><a name="section"></a> <span data-ttu-id="20661-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="20661-104">In This Section</span></span>  
 [<span data-ttu-id="20661-105">Comparar opções de armazenamento de blobs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="20661-105">Compare Options for Storing Blobs &#40;SQL Server&#41;</span></span>](compare-options-for-storing-blobs-sql-server.md)  
 <span data-ttu-id="20661-106">Compare as vantagens de FILESTREAM, FileTables e Remote Blob Store.</span><span class="sxs-lookup"><span data-stu-id="20661-106">Compare the advantages of FILESTREAM, FileTables, and Remote Blob Store.</span></span>  
  
 [<span data-ttu-id="20661-107">FILESTREAM &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="20661-107">FILESTREAM &#40;SQL Server&#41;</span></span>](filestream-sql-server.md)  
 <span data-ttu-id="20661-108">O FILESTREAM permite que aplicativos baseados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] armazenem dados não estruturados, como documentos e imagens, no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="20661-108">FILESTREAM enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-based applications to store unstructured data, such as documents and images, on the file system.</span></span> <span data-ttu-id="20661-109">Os aplicativos podem utilizar as APIs de streaming avançado e o desempenho do sistema de arquivos e, ao mesmo tempo, manter consistência transacional entre os dados não estruturados e os dados estruturados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="20661-109">Applications can leverage the rich streaming APIs and performance of the file system and at the same time maintain transactional consistency between the unstructured data and corresponding structured data.</span></span>  
  
 [<span data-ttu-id="20661-110">FileTables &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="20661-110">FileTables &#40;SQL Server&#41;</span></span>](filetables-sql-server.md)  
 <span data-ttu-id="20661-111">O recurso FileTable oferece suporte para namespace de arquivo do Windows e compatibilidade de aplicativos do Windows com dados de arquivo armazenados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20661-111">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="20661-112">O FileTable permite que um aplicativo integre seus componentes de armazenamento e gerenciamento de dados e forneça serviços integrados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , inclusive pesquisa de texto completo e pesquisa semântica, em dados não estruturados e metadados.</span><span class="sxs-lookup"><span data-stu-id="20661-112">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="20661-113">Em outras palavras, você pode armazenar arquivos e documentos em tabelas especiais no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , denominadas FileTables, mas acessá-los a partir de aplicativos do Windows como se eles estivessem armazenados no sistema de arquivos, sem fazer alterações nos seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="20661-113">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 [<span data-ttu-id="20661-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="20661-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](remote-blob-store-rbs-sql-server.md)  
 <span data-ttu-id="20661-115">O RBS (Remote BLOB Store) para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite que os administradores de bancos de dados armazenem BLOBs (objetos binários grandes) em soluções de armazenamento de mercadorias, e não diretamente no servidor.</span><span class="sxs-lookup"><span data-stu-id="20661-115">Remote BLOB store (RBS) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lets database administrators store binary large objects (BLOBs) in commodity storage solutions instead of directly on the server.</span></span> <span data-ttu-id="20661-116">Isso leva a uma grande economia de espaço e evita o desperdício de recursos caros de hardware de servidor.</span><span class="sxs-lookup"><span data-stu-id="20661-116">This saves a significant amount of space and avoids wasting expensive server hardware resources.</span></span> <span data-ttu-id="20661-117">O RBS fornece um conjunto de bibliotecas de API que definem um modelo padronizado para que aplicativos acessem dados BLOB.</span><span class="sxs-lookup"><span data-stu-id="20661-117">RBS provides a set of API libraries that define a standardized model for applications to access BLOB data.</span></span> <span data-ttu-id="20661-118">O RBS também inclui ferramentas de manutenção, como coleta de lixo, para ajudar a gerenciar dados BLOB remotos.</span><span class="sxs-lookup"><span data-stu-id="20661-118">RBS also includes maintenance tools, such as garbage collection, to help manage remote BLOB data.</span></span>  
  
 <span data-ttu-id="20661-119">O RBS está incluído na mídia de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mas não é instalado pelo programa de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20661-119">RBS is included on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
  
