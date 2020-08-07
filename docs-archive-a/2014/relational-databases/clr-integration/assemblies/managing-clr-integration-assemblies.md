---
title: Gerenciando assemblies de integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
ms.openlocfilehash: 191ccd73ca42ef4c26291e6de88f5f2b0cf565ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682278"
---
# <a name="managing-clr-integration-assemblies"></a><span data-ttu-id="689ba-102">Gerenciando assemblies de integração CLR</span><span class="sxs-lookup"><span data-stu-id="689ba-102">Managing CLR Integration Assemblies</span></span>
  <span data-ttu-id="689ba-103">O código gerenciado é compilado e implantado em unidades chamadas de assembly.</span><span class="sxs-lookup"><span data-stu-id="689ba-103">Managed code is compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="689ba-104">Um assembly é empacotado como uma DLL ou um arquivo executável (.exe).</span><span class="sxs-lookup"><span data-stu-id="689ba-104">An assembly is packaged as a DLL or executable (.exe) file.</span></span> <span data-ttu-id="689ba-105">Um arquivo executável pode ser executado sozinho, mas uma DLL precisa ser hospedada em um aplicativo existente.</span><span class="sxs-lookup"><span data-stu-id="689ba-105">While an executable file can run on its own, a DLL must be hosted in an existing application.</span></span> <span data-ttu-id="689ba-106">Os assemblies DLL gerenciados podem ser carregados e hospedados pelo [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="689ba-106">Managed DLL assemblies can be loaded into and hosted by [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="689ba-107">banco de dados usando a instrução CREATE ASSEMBLY, antes que possa ser carregado no processo e usado.</span><span class="sxs-lookup"><span data-stu-id="689ba-107">database using the CREATE ASSEMBLY statement, before it can be loaded in the process and used.</span></span> <span data-ttu-id="689ba-108">Os assemblies também podem ser atualizados de uma versão mais recente usando a instrução ALTER ASSEMBLY ou removidos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a instrução DROP ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="689ba-108">Assemblies can also be updated from a more recent version using the ALTER ASSEMBLY statement, or removed from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the DROP ASSEMBLY statement.</span></span>  
  
 <span data-ttu-id="689ba-109">As informações do assembly são armazenadas na tabela `sys.assembly_files` no banco de dados em que o assembly foi instalado.</span><span class="sxs-lookup"><span data-stu-id="689ba-109">Assembly information is stored in the `sys.assembly_files` table in the database where the assembly has been installed.</span></span> <span data-ttu-id="689ba-110">A tabela `sys.assembly_files` contém as colunas a seguir:</span><span class="sxs-lookup"><span data-stu-id="689ba-110">The `sys.assembly_files` table contains the following columns.</span></span>  
  
|<span data-ttu-id="689ba-111">Coluna</span><span class="sxs-lookup"><span data-stu-id="689ba-111">Column</span></span>|<span data-ttu-id="689ba-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="689ba-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="689ba-113">assembly_id</span><span class="sxs-lookup"><span data-stu-id="689ba-113">assembly_id</span></span>|<span data-ttu-id="689ba-114">O identificador definido para o assembly.</span><span class="sxs-lookup"><span data-stu-id="689ba-114">The identifier defined for the assembly.</span></span> <span data-ttu-id="689ba-115">Este número é atribuído a todos os objetos relacionados ao mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="689ba-115">This number is assigned to all objects relating to the same assembly.</span></span>|  
|<span data-ttu-id="689ba-116">name</span><span class="sxs-lookup"><span data-stu-id="689ba-116">name</span></span>|<span data-ttu-id="689ba-117">O nome do objeto.</span><span class="sxs-lookup"><span data-stu-id="689ba-117">The name of the object.</span></span>|  
|<span data-ttu-id="689ba-118">file_id</span><span class="sxs-lookup"><span data-stu-id="689ba-118">file_id</span></span>|<span data-ttu-id="689ba-119">Um número que identifica cada objeto, com o primeiro objeto associado a um determinado `assembly_id` recebendo o valor de 1.</span><span class="sxs-lookup"><span data-stu-id="689ba-119">A number identifying each object, with the first object associated with a given `assembly_id` being given the value of 1.</span></span> <span data-ttu-id="689ba-120">Se vários objetos forem associados ao mesmo `assembly_id`, cada valor `file_id` subsequente será incrementado em 1.</span><span class="sxs-lookup"><span data-stu-id="689ba-120">If multiple objects are associated with the same `assembly_id`, then each subsequent `file_id` value is incremented by 1.</span></span>|  
|<span data-ttu-id="689ba-121">conteúdo</span><span class="sxs-lookup"><span data-stu-id="689ba-121">content</span></span>|<span data-ttu-id="689ba-122">A representação hexadecimal do assembly ou arquivo.</span><span class="sxs-lookup"><span data-stu-id="689ba-122">The hexadecimal representation of the assembly or file.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="689ba-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="689ba-123">In This Section</span></span>  
 [<span data-ttu-id="689ba-124">Criando um assembly</span><span class="sxs-lookup"><span data-stu-id="689ba-124">Creating an Assembly</span></span>](creating-an-assembly.md)  
 <span data-ttu-id="689ba-125">Discute a criação de assemblies SAFE, EXTERNAL_ACCESS e UNSAFE CLR no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="689ba-125">Discusses creating SAFE, EXTERNAL_ACCESS, and UNSAFE CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="689ba-126">Alterando um assembly</span><span class="sxs-lookup"><span data-stu-id="689ba-126">Altering an Assembly</span></span>](altering-an-assembly.md)  
 <span data-ttu-id="689ba-127">Descreve a atualização de assemblies CLR no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="689ba-127">Describes updating CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="689ba-128">Descartando um assembly</span><span class="sxs-lookup"><span data-stu-id="689ba-128">Dropping an Assembly</span></span>](dropping-an-assembly.md)  
 <span data-ttu-id="689ba-129">Discute o descarte de assemblies CLR do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="689ba-129">Discusses dropping CLR assemblies from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="689ba-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="689ba-130">See Also</span></span>  
 <span data-ttu-id="689ba-131">[Segurança de integração CLR](../security/clr-integration-security.md) </span><span class="sxs-lookup"><span data-stu-id="689ba-131">[CLR Integration Security](../security/clr-integration-security.md) </span></span>  
 [<span data-ttu-id="689ba-132">Segurança de acesso a código da integração CLR</span><span class="sxs-lookup"><span data-stu-id="689ba-132">CLR Integration Code Access Security</span></span>](../security/clr-integration-code-access-security.md)  
  
  
