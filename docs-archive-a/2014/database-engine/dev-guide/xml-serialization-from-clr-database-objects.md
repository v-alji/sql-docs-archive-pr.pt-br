---
title: Serialização XML de objetos de banco de dados CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- serialization
- XML serialization [CLR integration]
- common language runtime [SQL Server], XML serialization
- XmlSerializer class
ms.assetid: ac84339b-9384-4710-bebc-01607864a344
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee93ee4b7bf9cba3f11b329244d4523636cb7704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681103"
---
# <a name="xml-serialization-from-clr-database-objects"></a><span data-ttu-id="97367-102">Serialização XML de objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="97367-102">XML Serialization from CLR Database Objects</span></span>
  <span data-ttu-id="97367-103">A serialização XML é necessária em dois cenários:</span><span class="sxs-lookup"><span data-stu-id="97367-103">XML serialization is required for two scenarios:</span></span>  
  
-   <span data-ttu-id="97367-104">Invocação de serviços da Web de objetos CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="97367-104">Invoking Web Services from common language runtime (CLR) objects.</span></span>  
  
-   <span data-ttu-id="97367-105">Conversão de um UDT (tipo definido pelo usuário) em XML.</span><span class="sxs-lookup"><span data-stu-id="97367-105">Converting a user-defined type (UDT) to XML.</span></span>  
  
 <span data-ttu-id="97367-106">A execução de serialização XML invocando a classe `XmlSerializer` normalmente gera um assembly de serialização adicional que é sobrecarregado no projeto com o assembly de origem.</span><span class="sxs-lookup"><span data-stu-id="97367-106">Performing XML serialization by invoking the `XmlSerializer` class normally generates an additional serialization assembly that is overloaded into the project with the source assembly.</span></span> <span data-ttu-id="97367-107">Entretanto, por questões de segurança, essa sobrecarga é desabilitada no CLR.</span><span class="sxs-lookup"><span data-stu-id="97367-107">However, for security purposes, this overload is disabled in the CLR.</span></span> <span data-ttu-id="97367-108">Portanto, para chamar um serviço Web ou executar a conversão de UDT em XML dentro [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do, o assembly deve ser criado manualmente usando uma ferramenta chamada **Sgen.exe** fornecida com o .NET Framework que gera os assemblies de serialização necessários.</span><span class="sxs-lookup"><span data-stu-id="97367-108">Therefore, to call a web service or perform conversion from UDT to XML inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the assembly must be created manually using a tool called **Sgen.exe** provided with the .NET Framework that generates the necessary serialization assemblies.</span></span> <span data-ttu-id="97367-109">Ao invocar `XmlSerializer`, o assembly de serialização precisa ser criado manualmente seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="97367-109">When invoking `XmlSerializer`, the serialization assembly must be created manually by following these steps:</span></span>  
  
1.  <span data-ttu-id="97367-110">Execute a ferramenta **Sgen.exe** fornecida com o SDK do .NET Framework para criar o assembly que contém os serializadores XML para o assembly de origem.</span><span class="sxs-lookup"><span data-stu-id="97367-110">Run the **Sgen.exe** tool that is provided with the .NET Framework SDK to create the assembly containing the XML serializers for the source assembly.</span></span>  
  
2.  <span data-ttu-id="97367-111">Registre o assembly gerado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a instrução `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="97367-111">Register the generated assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the `CREATE ASSEMBLY` statement.</span></span>  
  
 <span data-ttu-id="97367-112">Para obter informações sobre os erros que você pode receber ao executar a serialização XML, consulte o seguinte Suporte da Microsoft artigo: ["não é possível carregar o assembly de serialização gerado dinamicamente"](https://support.microsoft.com/kb/913668).</span><span class="sxs-lookup"><span data-stu-id="97367-112">For information about errors that you may receive when performing XML serialization, see the following Microsoft Support article: ["Cannot load dynamically generated serialization assembly"](https://support.microsoft.com/kb/913668).</span></span>  
  
 <span data-ttu-id="97367-113">Para obter informações sobre tipos de dados não suportados pelo XMLSerializer, consulte o suporte a associação de esquemas XML na documentação do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97367-113">For information on data types that are not supported by XMLSerializer, see XML Schema Binding Support in the .NET Framework in the .NET Framework documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97367-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97367-114">See Also</span></span>  
 <span data-ttu-id="97367-115">[Acesso a dados de objetos de banco de dado CLR](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="97367-115">[Data Access from CLR Database Objects](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="97367-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="97367-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
  
