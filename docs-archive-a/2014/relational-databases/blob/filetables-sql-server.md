---
title: FileTables (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 07/06/2016
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], overview
- FileTables [SQL Server]
- FileTable [SQL Server], see FileTables [SQL Server]
- FileTable [SQL Server]
ms.assetid: a57b629c-e9ed-48fd-9a48-ed3787d80c8f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0a38f0e947b0c4f68a49e13a40071f6a30cd07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684774"
---
# <a name="filetables-sql-server"></a><span data-ttu-id="79d63-102">FileTables (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="79d63-102">FileTables (SQL Server)</span></span>
  <span data-ttu-id="79d63-103">O recurso FileTable oferece suporte para namespace de arquivo do Windows e compatibilidade de aplicativos do Windows com dados de arquivo armazenados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79d63-103">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="79d63-104">O FileTable permite que um aplicativo integre seus componentes de armazenamento e gerenciamento de dados e forneça serviços integrados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , inclusive pesquisa de texto completo e pesquisa semântica, em dados não estruturados e metadados.</span><span class="sxs-lookup"><span data-stu-id="79d63-104">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="79d63-105">Em outras palavras, você pode armazenar arquivos e documentos em tabelas especiais no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , denominadas FileTables, mas acessá-los a partir de aplicativos do Windows como se eles estivessem armazenados no sistema de arquivos, sem fazer alterações nos seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="79d63-105">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 <span data-ttu-id="79d63-106">O recurso FileTable se baseia na tecnologia FILESTREAM do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79d63-106">The FileTable feature builds on top of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] FILESTREAM technology.</span></span> <span data-ttu-id="79d63-107">Para saber mais sobre o FILESTREAM, veja [FILESTREAM &#40;SQL Server&#41;](filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="79d63-107">To learn more about FILESTREAM, see [FILESTREAM &#40;SQL Server&#41;](filestream-sql-server.md).</span></span>  
  
##  <a name="benefits-of-the-filetable-feature"></a><a name="Goals"></a> <span data-ttu-id="79d63-108">Benefícios do recurso FileTable</span><span class="sxs-lookup"><span data-stu-id="79d63-108">Benefits of the FileTable Feature</span></span>  
 <span data-ttu-id="79d63-109">Os objetivos do recurso FileTable incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79d63-109">The goals of the FileTable feature include the following:</span></span>  
  
-   <span data-ttu-id="79d63-110">Compatibilidade com APIs do Windows para dados de arquivos armazenados em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79d63-110">Windows API compatibility for file data stored within a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="79d63-111">A compatibilidade com APIs do Windows inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79d63-111">Windows API compatibility includes the following:</span></span>  
  
    -   <span data-ttu-id="79d63-112">Acesso de streaming não transacional e atualizações in loco para dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="79d63-112">Non-transactional streaming access and in-place updates to FILESTREAM data.</span></span>  
  
    -   <span data-ttu-id="79d63-113">Um namespace hierárquico de diretórios e arquivos.</span><span class="sxs-lookup"><span data-stu-id="79d63-113">A hierarchical namespace of directories and files.</span></span>  
  
    -   <span data-ttu-id="79d63-114">Armazenamento de atributos de arquivo, como data de criação e data de modificação.</span><span class="sxs-lookup"><span data-stu-id="79d63-114">Storage of file attributes, such as created date and modified date.</span></span>  
  
    -   <span data-ttu-id="79d63-115">Suporte para APIs de gerenciamento de arquivos e diretórios do Windows.</span><span class="sxs-lookup"><span data-stu-id="79d63-115">Support for Windows file and directory management APIs.</span></span>  
  
-   <span data-ttu-id="79d63-116">Compatibilidade com outros recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que incluem ferramentas de gerenciamento, serviços e recursos de consulta relacional em dados de atributo de arquivo e FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="79d63-116">Compatibility with other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features including management tools, services, and relational query capabilities over FILESTREAM and file attribute data.</span></span>  
  
 <span data-ttu-id="79d63-117">Com isso, as FileTables removem uma barreira significativa ao uso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o armazenamento e gerenciamento de dados não estruturados que residem atualmente como arquivos em servidores de arquivos.</span><span class="sxs-lookup"><span data-stu-id="79d63-117">Thus FileTables remove a significant barrier to the use of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the storage and management of unstructured data that is currently residing as files on file servers.</span></span> <span data-ttu-id="79d63-118">As empresas podem mover esses dados de servidores de arquivos para FileTables para aproveitar a administração integrada e os serviços fornecidos pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79d63-118">Enterprises can move this data from file servers into FileTables to take advantage of integrated administration and services provided by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="79d63-119">Ao mesmo tempo, podem manter a compatibilidade de aplicativos do Windows para seus aplicativos do Windows existentes que consultam esses dados como arquivos no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="79d63-119">At the same time, they can maintain Windows application compatibility for their existing Windows applications that see this data as files in the file system.</span></span>  
    
##  <a name="what-is-a-filetable"></a><a name="Description"></a> <span data-ttu-id="79d63-120">O que é uma FileTable?</span><span class="sxs-lookup"><span data-stu-id="79d63-120">What Is a FileTable?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="79d63-121">oferece uma **tabela de arquivos**especial, também chamada de **FileTable**, para aplicativos que exigem o armazenamento de arquivos e diretório no banco de dados, com a compatibilidade de API do Windows e o acesso não transacional.</span><span class="sxs-lookup"><span data-stu-id="79d63-121">provides a special **table of files**, also referred to as a **FileTable**, for applications that require file and directory storage in the database, with Windows API compatibility and non-transactional access.</span></span> <span data-ttu-id="79d63-122">Uma FileTable é uma tabela de usuário especializada com um esquema predefinido que armazena dados FILESTREAM, além de informações de hierarquias de arquivos e diretórios e atributos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="79d63-122">A FileTable is a specialized user table with a pre-defined schema that stores FILESTREAM data, as well as file and directory hierarchy information and file attributes.</span></span>  
  
 <span data-ttu-id="79d63-123">Uma FileTable fornece a seguinte funcionalidade:</span><span class="sxs-lookup"><span data-stu-id="79d63-123">A FileTable provides the following functionality:</span></span>  
  
-   <span data-ttu-id="79d63-124">Uma FileTable representa uma hierarquia de diretórios e arquivos.</span><span class="sxs-lookup"><span data-stu-id="79d63-124">A FileTable represents a hierarchy of directories and files.</span></span> <span data-ttu-id="79d63-125">Armazena dados relacionados a todos os nós dessa hierarquia, tanto aos diretórios quanto aos arquivos que contêm.</span><span class="sxs-lookup"><span data-stu-id="79d63-125">It stores data related to all the nodes in that hierarchy, for both directories and the files they contain.</span></span> <span data-ttu-id="79d63-126">Essa hierarquia começa em um diretório raiz que você especifica ao criar a FileTable.</span><span class="sxs-lookup"><span data-stu-id="79d63-126">This hierarchy starts from a root directory that you specify when you create the FileTable.</span></span>  
  
-   <span data-ttu-id="79d63-127">Cada linha de uma FileTable representa um arquivo ou um diretório.</span><span class="sxs-lookup"><span data-stu-id="79d63-127">Every row in a FileTable represents a file or a directory.</span></span>  
  
-   <span data-ttu-id="79d63-128">Cada linha contém os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="79d63-128">Every row contains the following items.</span></span> <span data-ttu-id="79d63-129">Para obter mais informações sobre o esquema de uma FileTable, veja [Esquema de FileTable](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="79d63-129">For more information about the schema of a FileTable, see [FileTable Schema](filetable-schema.md).</span></span>  
  
    -   <span data-ttu-id="79d63-130">Uma coluna**file_stream** para dados de fluxo e um identificador (GUID) **stream_id** .</span><span class="sxs-lookup"><span data-stu-id="79d63-130">A**file_stream** column for stream data and a **stream_id** (GUID) identifier.</span></span> <span data-ttu-id="79d63-131">(A coluna **file_stream** é NULL para um diretório.)</span><span class="sxs-lookup"><span data-stu-id="79d63-131">(The **file_stream** column is NULL for a directory.)</span></span>  
  
    -   <span data-ttu-id="79d63-132">As colunas **path_locator** e **parent_path_locator** para representar e manter a hierarquia de arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="79d63-132">Both **path_locator** and **parent_path_locator** columns for representing and maintaining the file and directory hierarchy.</span></span>  
  
    -   <span data-ttu-id="79d63-133">10 atributos de arquivo, como a data de criação e a data de modificação que são úteis com APIs de E/S de arquivo.</span><span class="sxs-lookup"><span data-stu-id="79d63-133">10 file attributes such as created date and modified date that are useful with file I/O APIs.</span></span>  
  
    -   <span data-ttu-id="79d63-134">Uma coluna de tipo que oferece suporte à pesquisa de texto completo e à pesquisa semântica em arquivos e documentos.</span><span class="sxs-lookup"><span data-stu-id="79d63-134">A type column that supports full-text search and semantic search over files and documents.</span></span>  
  
-   <span data-ttu-id="79d63-135">Uma FileTable impõe determinados gatilhos e restrições definidos pelo sistema para manter a semântica de namespace de arquivo.</span><span class="sxs-lookup"><span data-stu-id="79d63-135">A FileTable enforces certain system-defined constraints and triggers to maintain file namespace semantics.</span></span>  
  
-   <span data-ttu-id="79d63-136">Quando o banco de dados é configurado para acesso não transacional, a hierarquia de arquivos e diretórios representada no FileTable é exposta no compartilhamento FILESTREAM configurado para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79d63-136">When the database is configured for non-transactional access, the file and directory hierarchy represented in the FileTable is exposed under the FILESTREAM share configured for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="79d63-137">Isso oferece ao sistema de arquivos acesso para aplicativos Windows.</span><span class="sxs-lookup"><span data-stu-id="79d63-137">This provides file system access for Windows applications.</span></span>  
  
 <span data-ttu-id="79d63-138">Algumas características adicionais de FileTables incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79d63-138">Some additional characteristics of FileTables include the following:</span></span>  
  
-   <span data-ttu-id="79d63-139">Os dados de arquivos e diretórios armazenados em uma FileTable são expostos através de um compartilhamento do Windows para acesso não transacional a arquivos para aplicativos baseados em APIs do Windows.</span><span class="sxs-lookup"><span data-stu-id="79d63-139">The file and directory data stored in a FileTable is exposed through a Windows share for non-transactional file access for Windows API based applications.</span></span> <span data-ttu-id="79d63-140">Para um aplicativo do Windows, isto parece um compartilhamento normal com seus arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="79d63-140">For a Windows application, this looks like a normal share with its files and directories.</span></span> <span data-ttu-id="79d63-141">Aplicativos podem usar um conjunto sofisticado de APIs do Windows para gerenciar os arquivos e diretórios neste compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="79d63-141">Applications can use a rich set of Windows APIs to manage the files and directories under this share.</span></span>  
  
-   <span data-ttu-id="79d63-142">A hierarquia de diretórios exposta por meio do compartilhamento é uma estrutura de diretórios puramente lógica que é mantida dentro da FileTable.</span><span class="sxs-lookup"><span data-stu-id="79d63-142">The directory hierarchy surfaced through the share is a purely logical directory structure that is maintained within the FileTable.</span></span>  
  
-   <span data-ttu-id="79d63-143">As chamadas para criar ou alterar um arquivo ou um diretório por meio do compartilhamento Windows são interceptadas por um componente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e refletidas nos dados relacionais correspondentes na FileTable.</span><span class="sxs-lookup"><span data-stu-id="79d63-143">Calls to create or change a file or directory through the Windows share are intercepted by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component and reflected in the corresponding relational data in the FileTable.</span></span>  
  
-   <span data-ttu-id="79d63-144">As operações de APIs do Windows são não transacionais por natureza, e não estão associadas a transações de usuário.</span><span class="sxs-lookup"><span data-stu-id="79d63-144">Windows API operations are non-transactional in nature, and are not associated with user transactions.</span></span> <span data-ttu-id="79d63-145">Entretanto, o acesso transacional a dados FILESTREAM armazenados em uma FileTable tem suporte total, como é o caso para qualquer coluna FILESTREAM em uma tabela normal.</span><span class="sxs-lookup"><span data-stu-id="79d63-145">However, transactional access to FILESTREAM data stored in a FileTable is fully supported, as is the case for any FILESTREAM column in a regular table.</span></span>  
  
-   <span data-ttu-id="79d63-146">FileTables também podem ser consultadas e atualizadas através do acesso [!INCLUDE[tsql](../../includes/tsql-md.md)] normal.</span><span class="sxs-lookup"><span data-stu-id="79d63-146">FileTables can also be queried and updated through normal [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="79d63-147">Elas também são integradas a ferramentas de gerenciamento e recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , como o backup.</span><span class="sxs-lookup"><span data-stu-id="79d63-147">They are also integrated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] management tools, and features such as backup.</span></span>  
  
  
##  <a name="additional-considerations-for-using-filetables"></a><a name="additional"></a> <span data-ttu-id="79d63-148">Considerações adicionais para usar FileTables</span><span class="sxs-lookup"><span data-stu-id="79d63-148">Additional Considerations for Using FileTables</span></span>  
  
###  <a name="administrative-considerations"></a><a name="DBA"></a> <span data-ttu-id="79d63-149">Considerações administrativas</span><span class="sxs-lookup"><span data-stu-id="79d63-149">Administrative Considerations</span></span>  
 <span data-ttu-id="79d63-150">**Sobre FILESTREAM e FileTables**</span><span class="sxs-lookup"><span data-stu-id="79d63-150">**About FILESTREAM and FileTables**</span></span>  
  
-   <span data-ttu-id="79d63-151">Você configura FileTables separadamente de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="79d63-151">You configure FileTables separately from FILESTREAM.</span></span> <span data-ttu-id="79d63-152">Portanto, você pode continuar a usar o recurso FILESTREAM sem habilitar o acesso não transacional ou criar FileTables.</span><span class="sxs-lookup"><span data-stu-id="79d63-152">Therefore you can continue to use the FILESTREAM feature without enabling non-transactional access or creating FileTables.</span></span>  
  
-   <span data-ttu-id="79d63-153">Não existe acesso não transacional a dados FILESTREAM, exceto por meio de FileTables.</span><span class="sxs-lookup"><span data-stu-id="79d63-153">There is no non-transactional access to FILESTREAM data except through FileTables.</span></span> <span data-ttu-id="79d63-154">Portanto, quando você habilita o acesso não transacional, o comportamento de colunas FILESTREAM e aplicativos existentes não é afetado.</span><span class="sxs-lookup"><span data-stu-id="79d63-154">Therefore, when you enable non-transactional access, the behavior of existing FILESTREAM columns and applications is not affected.</span></span>  
  
 <span data-ttu-id="79d63-155">**Sobre FileTables e acesso não transacional**</span><span class="sxs-lookup"><span data-stu-id="79d63-155">**About FileTables and non-transactional access**</span></span>  
  
-   <span data-ttu-id="79d63-156">É possível habilitar ou desabilitar o acesso não transacional no nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="79d63-156">You can enable or disable non-transactional access at the database level.</span></span>  
  
-   <span data-ttu-id="79d63-157">Você pode configurar ou ajustar o acesso não transacional no nível de banco de dados desativando-o, ou habilitando o acesso somente leitura ou leitura/gravação completa.</span><span class="sxs-lookup"><span data-stu-id="79d63-157">You can configure or fine-tune non-transactional access at the database level by turning it off, or by enabling read only or full read/write access.</span></span>  
  
  
###  <a name="filetables-do-not-support-memory-mapped-files"></a><a name="memory"></a> <span data-ttu-id="79d63-158">FileTables não dão suporte a arquivos mapeados por memória</span><span class="sxs-lookup"><span data-stu-id="79d63-158">FileTables Do Not Support Memory-Mapped Files</span></span>  
 <span data-ttu-id="79d63-159">FileTables não dão suporte a arquivos mapeados por memória.</span><span class="sxs-lookup"><span data-stu-id="79d63-159">FileTables do not support memory-mapped files.</span></span> <span data-ttu-id="79d63-160">Bloco de Notas e Paint são dois exemplos comuns de aplicativos que usam arquivos mapeados por memória.</span><span class="sxs-lookup"><span data-stu-id="79d63-160">Notepad and Paint are two common examples of applications that use memory-mapped files.</span></span> <span data-ttu-id="79d63-161">Você não pode usar estes aplicativos no mesmo computador que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para abrir arquivos que estão armazenados em um FileTable.</span><span class="sxs-lookup"><span data-stu-id="79d63-161">You cannot use these applications on the same computer as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open files that are stored in a FileTable.</span></span> <span data-ttu-id="79d63-162">Porém, você pode usar estes aplicativos de um computador remoto para abrir arquivos que estão armazenados em um FileTable, porque, nestes circunstâncias, o recurso do mapeamento de memória não é usado.</span><span class="sxs-lookup"><span data-stu-id="79d63-162">However you can use these applications from a remote computer to open files that are stored in a FileTable, because in these circumstances the memory-mapping feature is not used.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="79d63-163">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="79d63-163">Related Tasks</span></span>  
 [<span data-ttu-id="79d63-164">Habilitar os pré-requisitos para o FileTable</span><span class="sxs-lookup"><span data-stu-id="79d63-164">Enable the Prerequisites for FileTable</span></span>](enable-the-prerequisites-for-filetable.md)  
 <span data-ttu-id="79d63-165">Descreve como habilitar os pré-requisitos para criar e usar FileTables.</span><span class="sxs-lookup"><span data-stu-id="79d63-165">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
 [<span data-ttu-id="79d63-166">Criar, alterar e remover FileTables</span><span class="sxs-lookup"><span data-stu-id="79d63-166">Create, Alter, and Drop FileTables</span></span>](create-alter-and-drop-filetables.md)  
 <span data-ttu-id="79d63-167">Descreve como criar uma nova FileTable, ou alterar ou remover uma FileTable existente.</span><span class="sxs-lookup"><span data-stu-id="79d63-167">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
 [<span data-ttu-id="79d63-168">Carregar arquivos em FileTables</span><span class="sxs-lookup"><span data-stu-id="79d63-168">Load Files into FileTables</span></span>](load-files-into-filetables.md)  
 <span data-ttu-id="79d63-169">Descreve como carregar ou migrar arquivos para FileTables.</span><span class="sxs-lookup"><span data-stu-id="79d63-169">Describes how to load or migrate files into FileTables.</span></span>  
  
 [<span data-ttu-id="79d63-170">Trabalhar com diretórios e caminhos em FileTables</span><span class="sxs-lookup"><span data-stu-id="79d63-170">Work with Directories and Paths in FileTables</span></span>](work-with-directories-and-paths-in-filetables.md)  
 <span data-ttu-id="79d63-171">Descreve a estrutura de diretórios na qual os arquivos são armazenados em FileTables.</span><span class="sxs-lookup"><span data-stu-id="79d63-171">Describes the directory structure in which the files are stored in FileTables.</span></span>  
  
 [<span data-ttu-id="79d63-172">Acessar FileTables com Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="79d63-172">Access FileTables with Transact-SQL</span></span>](access-filetables-with-transact-sql.md)  
 <span data-ttu-id="79d63-173">Descreve como os comandos DML (linguagem de manipulação de dados) Transact-SQL funcionam com FileTables.</span><span class="sxs-lookup"><span data-stu-id="79d63-173">Describes how Transact-SQL data manipulation language (DML) commands work with FileTables.</span></span>  
  
 [<span data-ttu-id="79d63-174">Acessar FileTables com APIs de entrada e saída de arquivo</span><span class="sxs-lookup"><span data-stu-id="79d63-174">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
 <span data-ttu-id="79d63-175">Descreve como a E/S do sistema de arquivos funciona em uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="79d63-175">Describes how file system I/O works on a FileTable.</span></span>  
  
 [<span data-ttu-id="79d63-176">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="79d63-176">Manage FileTables</span></span>](manage-filetables.md)  
 <span data-ttu-id="79d63-177">Descreve tarefas administrativas comuns para gerenciar FileTables.</span><span class="sxs-lookup"><span data-stu-id="79d63-177">Describes common administrative tasks for managing FileTables.</span></span>  
  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="79d63-178">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="79d63-178">Related Content</span></span>  
 [<span data-ttu-id="79d63-179">Esquema de FileTable</span><span class="sxs-lookup"><span data-stu-id="79d63-179">FileTable Schema</span></span>](filetable-schema.md)  
 <span data-ttu-id="79d63-180">Descreve o esquema predefinido e fixo de uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="79d63-180">Describes the pre-defined and fixed schema of a FileTable.</span></span>  
  
 [<span data-ttu-id="79d63-181">Compatibilidade do FileTable com outros recursos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="79d63-181">FileTable Compatibility with Other SQL Server Features</span></span>](filetable-compatibility-with-other-sql-server-features.md)  
 <span data-ttu-id="79d63-182">Descreve como as FileTables funcionam com outros recursos do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="79d63-182">Describes how FileTables work with other features of SQL Server.</span></span>  
  
 [<span data-ttu-id="79d63-183">DDL, funções, procedimentos armazenados e exibições de FileTable</span><span class="sxs-lookup"><span data-stu-id="79d63-183">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="79d63-184">Lista as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] e os objetos de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que foram adicionados ou alterados para oferecer suporte ao recurso FileTable.</span><span class="sxs-lookup"><span data-stu-id="79d63-184">Lists the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that have been added or changed to support the FileTable feature.</span></span>  
  
 
  
