# Hibernate-One-to-One-Uni-Direction

- Bu projede Hibernate ile One-to-One (Uni-Directional) Mapping uygulaması yapılmıştır

- İki adet veritabanına tablo oluşturulup yabancı anahtar(Foreign Key) ilişkisi kurulmuştur
- Daha sonra tablolardaki eğitmen ve eğitmen detayı sınıfı, hepsini bir araya getirmek için ana uygulama sınıfı oluşturulmuştur

```
CREATE TABLE `instructor_detail` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`youtube_channel` varchar(128) DEFAULT NULL,
`hobby` varchar(45) DEFAULT NULL,
PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=latin1;

CREATE TABLE `instructor` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`first_name` varchar(45) DEFAULT NULL,
`last_name` varchar(45) DEFAULT NULL,
`email` varchar(45) DEFAULT NULL,
`instructor_detail_id` int(11) DEFAULT NULL,
PRIMARY KEY (`id`),
KEY `FK_DETAIL_idx` (`instructor_detail_id`),
CONSTRAINT `FK_DETAIL` FOREIGN KEY (`instructor_detail_id`) REFERENCES `instructor_detail` (`id`) ON DELETE NO ACTION ON UPDATE NO ACTION
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=latin1;
```
