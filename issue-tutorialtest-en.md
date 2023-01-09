## General

- [ ] An example project for Maui can be created and added [here](https://docs.abp.io/en/commercial/latest/tutorials/book-store/part-1?UI=MAUIBlazor&DB=EF#download-the-source-code).

- [ ] The `Acme.BookStore.Blazor` namespace everywhere should be changed to `Acme.BookStore.MauiBlazor`

- [ ] Login and homepage screenshots are old [here](https://docs.abp.io/en/commercial/latest/getting-started-running-solution?UI=MAUIBlazor&DB=EF&Tiered=No)


## Part-2

- [ ] The image [here](https://docs.abp.io/en/commercial/latest/tutorials/book-store/part-2?UI=MAUIBlazor&DB=EF#create-a-books-page) returns 404.


## Part-3

- [ ] The marked places [here](https://docs.abp.io/en/commercial/latest/tutorials/book-store/part-3?UI=MAUIBlazor&DB=EF#automapper-configuration) should be corrected.
![](https://user-images.githubusercontent.com/58659931/211317012-e0b4bfa8-c755-472a-bc0f-de9a2e29cb58.png)

- [ ] Auto mapper configuration missing in MauiBlazor project. https://github.com/volosoft/volo/issues/13151

## Part-10

- [ ] The code [here](https://docs.abp.io/en/commercial/latest/tutorials/book-store/part-10?UI=MAUIBlazor&DB=EF#createupdatebookdto)
```csharp
public Guid AuthorId { get; set; }
```
should be changed to
```csharp
[Required]
public Guid AuthorId { get; set; }
```
for accuracy.

- [ ] There is a missing } at the end of the code [here](https://docs.abp.io/en/commercial/latest/tutorials/book-store/part-10?UI=MAUIBlazor&DB=EF#unit-tests).


- [ ] When entering the book name, it makes the input green as if the author is selected, but if it is not selected and an attempt is made to add it, an error occurs and the error message is not unfriendly. ![](https://user-images.githubusercontent.com/58659931/211317194-5ac6fb8c-6d3b-46bf-9999-821faa03b40f.png)
