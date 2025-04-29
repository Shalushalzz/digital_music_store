-- create database digital_music_store
USE digital_music_store;

CREATE TABLE Customer (
    customer_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    registration_date DATE
);

CREATE TABLE Artist (
    artist_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE Album (
    album_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100),
    release_year YEAR,
    artist_id INT,
    FOREIGN KEY (artist_id) REFERENCES Artist(artist_id)
);

CREATE TABLE Genre (
    genre_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50)
);

CREATE TABLE Song (
    song_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100),
    duration TIME,
    price DECIMAL(5,2),
    album_id INT,
    genre_id INT,
    FOREIGN KEY (album_id) REFERENCES Album(album_id),
    FOREIGN KEY (genre_id) REFERENCES Genre(genre_id)
);

CREATE TABLE Purchase (
    purchase_id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT,
    purchase_date DATE,
    total_amount DECIMAL(8,2),
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id)
);

CREATE TABLE PurchaseDetail (
    purchase_id INT,
    song_id INT,
    PRIMARY KEY (purchase_id, song_id),
    FOREIGN KEY (purchase_id) REFERENCES Purchase(purchase_id),
    FOREIGN KEY (song_id) REFERENCES Song(song_id)
);

CREATE TABLE Playlist (
    playlist_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    customer_id INT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id)
);

CREATE TABLE PlaylistSong (
    playlist_id INT,
    song_id INT,
    PRIMARY KEY (playlist_id, song_id),
    FOREIGN KEY (playlist_id) REFERENCES Playlist(playlist_id),
    FOREIGN KEY (song_id) REFERENCES Song(song_id)
);

CREATE TABLE Review (
    review_id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT,
    song_id INT,
    rating INT CHECK (rating BETWEEN 1 AND 5),
    comment TEXT,
    review_date DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id),
    FOREIGN KEY (song_id) REFERENCES Song(song_id)
);

CREATE TABLE Payment (
    payment_id INT AUTO_INCREMENT PRIMARY KEY,
    purchase_id INT,
    method VARCHAR(50),
    status VARCHAR(20),
    payment_date DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (purchase_id) REFERENCES Purchase(purchase_id)
);

CREATE TABLE Subscription (
    subscription_id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT,
    plan VARCHAR(50),
    start_date DATE,
    end_date DATE,
    is_active BOOLEAN,
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id)
);

-- inserting the datas for the column in a table
INSERT INTO customer (customer_id, name, email, registration_date) VALUES
(1, 'Aarav Patel', 'aarav.patel@email.com', '2024-01-05'),
(2, 'Diya Sharma', 'diya.sharma@email.com', '2024-01-12'),
(3, 'Rohan Verma', 'rohan.verma@email.com', '2024-01-19'),
(4, 'Siya Kapoor', 'siya.kapoor@email.com', '2024-01-26'),
(5, 'Arjun Singh', 'arjun.singh@email.com', '2024-02-02'),
(6, 'Anika Yadav', 'anika.yadav@email.com', '2024-02-09'),
(7, 'Aryan Mishra', 'aryan.mishra@email.com', '2024-02-16'),
(8, 'Priya Tiwari', 'priya.tiwari@email.com', '2024-02-23'),
(9, 'Karan Kumar', 'karan.kumar@email.com', '2024-03-02'),
(10, 'Neha Joshi', 'neha.joshi@email.com', '2024-03-09'),
(11, 'Vikram Gupta', 'vikram.gupta@email.com', '2024-03-16'),
(12, 'Ishika Bajaj', 'ishika.bajaj@email.com', '2024-03-23'),
(13, 'Advait Reddy', 'advait.reddy@email.com', '2024-03-30'),
(14, 'Tanvi Iyer', 'tanvi.iyer@email.com', '2024-04-06'),
(15, 'Dhruv Menon', 'dhruv.menon@email.com', '2024-04-13'),
(16, 'Meera Pillai', 'meera.pillai@email.com', '2024-04-20'),
(17, 'Rishi Nair', 'rishi.nair@email.com', '2024-04-27'),
(18, 'Sanya Choudhury', 'sanya.choudhury@email.com', '2024-05-04'),
(19, 'Varun Dutta', 'varun.dutta@email.com', '2024-05-11'),
(20, 'Aanya Gill', 'aanya.gill@email.com', '2024-05-18'),
(21, 'Kabir Malhotra', 'kabir.malhotra@email.com', '2024-05-25'),
(22, 'Kyra Sethi', 'kyra.sethi@email.com', '2024-06-01'),
(23, 'Laksh Bajaj', 'laksh.bajaj@email.com', '2024-06-08'),
(24, 'Leela Subramaniam', 'leela.subramaniam@email.com', '2024-06-15'),
(25, 'Mihir Gowda', 'mihir.gowda@email.com', '2024-06-22'),
(26, 'Mira Srinivasan', 'mira.srinivasan@email.com', '2024-06-29'),
(27, 'Nakul Raghunathan', 'nakul.raghunathan@email.com', '2024-07-06'),
(28, 'Navya Venkatesan', 'navya.venkatesan@email.com', '2024-07-13'),
(29, 'Omkar Krishnamurthy', 'omkar.krishnamurthy@email.com', '2024-07-20'),
(30, 'Pallavi Chandrasekhar', 'pallavi.chandrasekhar@email.com', '2024-07-27'),
(31, 'Parth Joshi', 'parth.joshi@email.com', '2024-08-03'),
(32, 'Pooja Patel', 'pooja.patel@email.com', '2024-08-10'),
(33, 'Pranav Sharma', 'pranav.sharma@email.com', '2024-08-17'),
(34, 'Prisha Verma', 'prisha.verma@email.com', '2024-08-24'),
(35, 'Rahul Kapoor', 'rahul.kapoor@email.com', '2024-08-31'),
(36, 'Raina Singh', 'raina.singh@email.com', '2024-09-07'),
(37, 'Rajiv Yadav', 'rajiv.yadav@email.com', '2024-09-14'),
(38, 'Riya Mishra', 'riya.mishra@email.com', '2024-09-21'),
(39, 'Sameer Tiwari', 'sameer.tiwari@email.com', '2024-09-28'),
(40, 'Samira Kumar', 'samira.kumar@email.com', '2024-10-05'),
(41, 'Siddharth Gupta', 'siddharth.gupta@email.com', '2024-10-12'),
(42, 'Simran Bajaj', 'simran.bajaj@email.com', '2024-10-19'),
(43, 'Soham Reddy', 'soham.reddy@email.com', '2024-10-26'),
(44, 'Sonali Iyer', 'sonali.iyer@email.com', '2024-11-02'),
(45, 'Srikant Menon', 'srikant.menon@email.com', '2024-11-09'),
(46, 'Srishti Pillai', 'srishti.pillai@email.com', '2024-11-16'),
(47, 'Suraj Nair', 'suraj.nair@email.com', '2024-11-23'),
(48, 'Surabhi Choudhury', 'surabhi.choudhury@email.com', '2024-11-30'),
(49, 'Tarun Dutta', 'tarun.dutta@email.com', '2024-12-07'),
(50, 'Trisha Gill', 'trisha.gill@email.com', '2024-12-14'),
(51, 'Anaya Sharma', 'anaya.sharma@email.com', '2025-01-03'),
(52, 'Dev Patel', 'dev.patel@email.com', '2025-01-10'),
(53, 'Esha Verma', 'esha.verma@email.com', '2025-01-17'),
(54, 'Farhan Kapoor', 'farhan.kapoor@email.com', '2025-01-24'),
(55, 'Gauri Singh', 'gauri.singh@email.com', '2025-01-31'),
(56, 'Harsh Yadav', 'harsh.yadav@email.com', '2025-02-07'),
(57, 'Ira Mishra', 'ira.mishra@email.com', '2025-02-14'),
(58, 'Jai Tiwari', 'jai.tiwari@email.com', '2025-02-21'),
(59, 'Kavya Kumar', 'kavya.kumar@email.com', '2025-02-28'),
(60, 'Luv Joshi', 'luv.joshi@email.com', '2025-03-07'),
(61, 'Mansi Gupta', 'mansi.gupta@email.com', '2025-03-14'),
(62, 'Neil Bajaj', 'neil.bajaj@email.com', '2025-03-21'),
(63, 'Nina Reddy', 'nina.reddy@email.com', '2025-03-28'),
(64, 'Ojas Iyer', 'ojas.iyer@email.com', '2025-04-04'),
(65, 'Payal Menon', 'payal.menon@email.com', '2025-04-11'),
(66, 'Qasim Pillai', 'qasim.pillai@email.com', '2025-04-18'),
(67, 'Riya Sharma', 'riya.sharma2@email.com', '2025-04-25');

-- inserting the datas for the column in a table
INSERT INTO artist (artist_id, name) VALUES
(101, 'Arijit Singh'),
(102, 'Shreya Ghoshal'),
(103, 'Sonu Nigam'),
(104, 'Sunidhi Chauhan'),
(105, 'Lata Mangeshkar'),
(106, 'Kishore Kumar'),
(107, 'Mohammed Rafi'),
(108, 'Asha Bhosle'),
(109, 'KK'),
(110, 'Atif Aslam'),
(111, 'Taylor Swift'),
(112, 'Ed Sheeran'),
(113, 'Beyoncé'),
(114, 'Drake'),
(115, 'Rihanna'),
(116, 'Justin Bieber'),
(117, 'Ariana Grande'),
(118, 'The Weeknd'),
(119, 'Billie Eilish'),
(120, 'Harry Styles'),
(121, 'Coldplay'),
(122, 'Maroon 5'),
(123, 'Imagine Dragons'),
(124, 'Linkin Park'),
(125, 'Queen'),
(126, 'The Beatles'),
(127, 'The Rolling Stones'),
(128, 'Led Zeppelin'),
(129, 'Pink Floyd'),
(130, 'Nirvana'),
(131, 'BTS'),
(132, 'Blackpink'),
(133, 'Twice'),
(134, 'Stray Kids'),
(135, 'TXT'),
(136, 'NCT'),
(137, 'Seventeen'),
(138, 'EXO'),
(139, 'Red Velvet'),
(140, 'BigBang'),
(141, 'Yo Yo Honey Singh'),
(142, 'Badshah'),
(143, 'Neha Kakkar'),
(144, 'Guru Randhawa'),
(145, 'Armaan Malik'),
(146, 'Benny Dayal'),
(147, 'Shalmali Kholgade'),
(148, 'Amit Trivedi'),
(149, 'Pritam'),
(150, 'AR Rahman');
-- create table genre
create table genre(
genre_id primary key not null
name varchar(40) not null);
-- inserting the datas for the column in a table
INSERT INTO genre (genre_id,name) VALUES
(201, 'Pop'),
(202, 'Rock'),
(203, 'Hip-Hop'),
(204, 'R&B'),
(205, 'Country'),
(206, 'Jazz'),
(207, 'Classical'),
(208, 'Electronic'),
(209, 'Folk'),
(210, 'Blues'),
(211, 'Indie'),
(212, 'Alternative'),
(213, 'Metal'),
(214, 'Punk'),
(215, 'Reggae'),
(216, 'Disco'),
(217, 'Funk'),
(218, 'Soul'),
(219, 'Gospel'),
(220, 'Opera'),
(221, 'Symphony'),
(222, 'Concerto'),
(223, 'Sonata'),
(224, 'Waltz'),
(225, 'Polka'),
(226, 'March'),
(227, 'Ragtime'),
(228, 'Swing'),
(229, 'Bebop'),
(230, 'Latin'),
(231, 'Salsa'),
(232, 'Tango'),
(233, 'Flamenco'),
(234, 'Cumbia'),
(235, 'Merengue'),
(236, 'Reggaeton'),
(237, 'K-Pop'),
(238, 'J-Pop'),
(239, 'C-Pop'),
(240, 'Bollywood'),
(241, 'Tollywood'),
(242, 'Kollywood'),
(243, 'Sandalwood'),
(244, 'Mollywood'),
(245, 'Bhangra'),
(246, 'Qawwali'),
(247, 'Ghazal'),
(248, 'Devotional'),
(249, 'Fusion'),
(250, 'Ambient');

-- inserting the datas for the column in a table
INSERT INTO album (album_id, title, release_year, artist_id) VALUES
(301, 'Romance Forever', 2024, 101),  -- Arijit Singh
(302, 'Melody Queen', 2024, 102),     -- Shreya Ghoshal
(303, 'Golden Hits', 2023, 103),      -- Sonu Nigam
(304, 'Diva Unplugged', 2025, 104),   -- Sunidhi Chauhan
(305, 'Timeless Voice', 2022, 105),   -- Lata Mangeshkar
(306, 'Evergreen', 2021, 106),        -- Kishore Kumar
(307, 'Sufi Magic', 2024, 107),       -- Mohammed Rafi
(308, 'Retro Remix', 2025, 108),      -- Asha Bhosle
(309, 'Heartbeats', 2024, 109),       -- KK
(310, 'Love Ballads', 2023, 110),     -- Atif Aslam
(311, 'Fearless', 2021, 111),         -- Taylor Swift
(312, 'Perfect', 2022, 112),          -- Ed Sheeran
(313, 'Lemonade', 2016, 113),         -- Beyoncé
(314, 'Views', 2016, 114),             -- Drake
(315, 'Anti', 2016, 115),              -- Rihanna
(316, 'Purpose', 2015, 116),          -- Justin Bieber
(317, 'Thank U, Next', 2019, 117),    -- Ariana Grande
(318, 'Starboy', 2016, 118),          -- The Weeknd
(319, 'When We All Fall Asleep, Where Do We Go?', 2019, 119), -- Billie Eilish
(320, 'Fine Line', 2019, 120),        -- Harry Styles
(321, 'Parachutes', 2000, 121),       -- Coldplay
(322, 'Songs About Jane', 2002, 122), -- Maroon 5
(323, 'Night Visions', 2012, 123),    -- Imagine Dragons
(324, 'Hybrid Theory', 2000, 124),    -- Linkin Park
(325, 'A Night at the Opera', 1975, 125), -- Queen
(326, 'Abbey Road', 1969, 126),       -- The Beatles
(327, 'Sticky Fingers', 1971, 127),   -- The Rolling Stones
(328, 'IV', 1971, 128),               -- Led Zeppelin
(329, 'The Dark Side of the Moon', 1973, 129), -- Pink Floyd
(330, 'Nevermind', 1991, 130),       -- Nirvana
(331, 'Map of the Soul: Persona', 2019, 131), -- BTS
(332, 'Kill This Love', 2019, 132),   -- Blackpink
(333, 'Formula of Love: O+T=3', 2021, 133), -- Twice
(334, 'Oddinary', 2022, 134),         -- Stray Kids
(335, 'The Chaos Chapter: FREEZE', 2021, 135), -- TXT
(336, 'Universe', 2021, 136),         -- NCT
(337, 'Face the Sun', 2022, 137),     -- Seventeen
(338, 'The War', 2017, 138),          -- EXO
(339, 'Perfect Velvet', 2017, 139),   -- Red Velvet
(340, 'MADE', 2016, 140),             -- BigBang
(341, 'International Villager', 2011, 141), -- Yo Yo Honey Singh
(342, 'ONE', 2023, 142),              -- Badshah
(343, 'Khamoshiyan', 2015, 143),      -- Neha Kakkar
(344, 'High Rated Gabru', 2017, 144),  -- Guru Randhawa
(345, 'Hero', 2015, 145),             -- Armaan Malik
(346, 'Rock On!!', 2008, 146),        -- Benny Dayal
(347, 'Race 2', 2013, 147),           -- Shalmali Kholgade
(348, 'Dev.D', 2009, 148),            -- Amit Trivedi
(349, 'Life in a... Metro', 2007, 149), -- Pritam
(350, 'Rockstar', 2011, 150);         -- AR Rahman

-- inserting the datas for the column in a table
INSERT INTO admin (admin_id, username, password_hash, email, created_at) VALUES
(401, 'admin123', 'hashed_password_1', 'admin1@musicstore.com', '2025-04-20 10:00:00'),
(402, 'superAdmin', 'hashed_password_2', 'superadmin@musicstore.com', '2025-04-21 14:30:00'),
(403, 'musicMod', 'hashed_password_3', 'musicmod@musicstore.com', '2025-04-21 16:00:00'),
(404, 'userAdmin', 'hashed_password_4', 'useradmin@musicstore.com', '2025-04-22 09:00:00'),
(405, 'contentManager', 'hashed_password_5', 'contentman@musicstore.com', '2025-04-22 13:00:00'),
(406, 'techSupport', 'hashed_password_6', 'techsupport@musicstore.com', '2025-04-22 18:00:00'),
(407, 'dataAnalyst', 'hashed_password_7', 'dataanalyst@musicstore.com', '2025-04-23 08:00:00'),
(408, 'reportAdmin', 'hashed_password_8', 'reportadmin@musicstore.com', '2025-04-23 11:00:00'),
(409, 'financeDept', 'hashed_password_9', 'finance@musicstore.com', '2025-04-23 15:00:00'),
(410, 'marketingTeam', 'hashed_password_10', 'marketing@musicstore.com', '2025-04-23 17:00:00'),
(411, 'adminBackup', 'hashed_password_11', 'adminbackup@musicstore.com', '2025-04-23 19:00:00'),
(412, 'levelOneSupport', 'hashed_password_12', 'level1support@musicstore.com', '2025-04-23 20:00:00'),
(413, 'levelTwoSupport', 'hashed_password_13', 'level2support@musicstore.com', '2025-04-23 21:00:00'),
(414, 'contentReviewer', 'hashed_password_14', 'contentreview@musicstore.com', '2025-04-23 22:00:00'),
(415, 'systemAdmin', 'hashed_password_15', 'systemadmin@musicstore.com', '2025-04-23 23:00:00'),
(416, 'networkAdmin', 'hashed_password_16', 'networkadmin@musicstore.com', '2025-04-24 00:00:00'),
(417, 'databaseAdmin', 'hashed_password_17', 'databaseadmin@musicstore.com', '2025-04-24 01:00:00'),
(418, 'securityAdmin', 'hashed_password_18', 'securityadmin@musicstore.com', '2025-04-24 02:00:00'),
(419, 'webmaster', 'hashed_password_19', 'webmaster@musicstore.com', '2025-04-24 03:00:00'),
(420, 'developer', 'hashed_password_20', 'developer@musicstore.com', '2025-04-24 04:00:00'),
(421, 'designer', 'hashed_password_21', 'designer@musicstore.com', '2025-04-24 05:00:00'),
(422, 'qaTester', 'hashed_password_22', 'qatester@musicstore.com', '2025-04-24 06:00:00'),
(423, 'projectManager', 'hashed_password_23', 'projectmanager@musicstore.com', '2025-04-24 07:00:00'),
(424, 'businessAnalyst', 'hashed_password_24', 'businessanalyst@musicstore.com', '2025-04-24 08:00:00'),
(425, 'hrManager', 'hashed_password_25', 'hrmanager@musicstore.com', '2025-04-24 09:00:00'),
(426, 'recruiter', 'hashed_password_26', 'recruiter@musicstore.com', '2025-04-24 10:00:00'),
(427, 'trainer', 'hashed_password_27', 'trainer@musicstore.com', '2025-04-24 11:00:00'),
(428, 'payrollSpecialist', 'hashed_password_28', 'payroll@musicstore.com', '2025-04-24 12:00:00'),
(429, 'legalCounsel', 'hashed_password_29', 'legal@musicstore.com', '2025-04-24 13:00:00'),
(430, 'complianceOfficer', 'hashed_password_30', 'compliance@musicstore.com', '2025-04-24 14:00:00'),
(431, 'salesRepresentative', 'hashed_password_31', 'salesrep@musicstore.com', '2025-04-24 15:00:00'),
(432, 'customerServiceRep', 'hashed_password_32', 'customerservice@musicstore.com', '2025-04-24 16:00:00'),
(433, 'publicRelations', 'hashed_password_33', 'publicrelations@musicstore.com', '2025-04-24 17:00:00'),
(434, 'eventCoordinator', 'hashed_password_34', 'eventcoordinator@musicstore.com', '2025-04-24 18:00:00'),
(435, 'graphicDesigner', 'hashed_password_35', 'graphicdesigner@musicstore.com', '2025-04-24 19:00:00'),
(436, 'copywriter', 'hashed_password_36', 'copywriter@musicstore.com', '2025-04-24 20:00:00'),
(437, 'socialMediaManager', 'hashed_password_37', 'socialmediamanager@musicstore.com', '2025-04-24 21:00:00'),
(438, 'seoSpecialist', 'hashed_password_38', 'seospecialist@musicstore.com', '2025-04-24 22:00:00'),
(439, 'emailMarketing', 'hashed_password_39', 'emailmarketing@musicstore.com', '2025-04-24 23:00:00'),
(440, 'affiliateMarketing', 'hashed_password_40', 'affiliatemarketing@musicstore.com', '2025-04-25 00:00:00'),
(441, 'dataEntryClerk', 'hashed_password_41', 'dataentry@musicstore.com', '2025-04-25 01:00:00'),
(442, 'officeManager', 'hashed_password_42', 'officemanager@musicstore.com', '2025-04-25 02:00:00'),
(443, 'receptionist', 'hashed_password_43', 'receptionist@musicstore.com', '2025-04-25 03:00:00'),
(444, 'janitor', 'hashed_password_44', 'janitor@musicstore.com', '2025-04-25 04:00:00'),
(445, 'securityGuard', 'hashed_password_45', 'securityguard@musicstore.com', '2025-04-25 05:00:00'),
(446, 'driver', 'hashed_password_46', 'driver@musicstore.com', '2025-04-25 06:00:00'),
(447, 'chef', 'hashed_password_47', 'chef@musicstore.com', '2025-04-25 07:00:00'),
(448, 'waiter', 'hashed_password_48', 'waiter@musicstore.com', '2025-04-25 08:00:00'),
(449, 'bartender', 'hashed_password_49', 'bartender@musicstore.com', '2025-04-25 09:00:00'),
(450, 'musician', 'hashed_password_50', 'musician@musicstore.com', '2025-04-25 10:00:00');

-- inserting the datas for the column in a table
INSERT INTO purchase (purchase_id, customer_id, purchase_date, total_amount) VALUES
(2001, 1, '2025-04-23', 15.99),
(2002, 5, '2025-04-22', 10.50),
(2003, 10, '2025-04-21', 22.75),
(2004, 15, '2025-04-20', 8.20),
(2005, 20, '2025-04-19', 12.00),
(2006, 25, '2025-04-18', 18.40),
(2007, 30, '2025-04-17', 9.99),
(2008, 35, '2025-04-16', 14.65),
(2009, 40, '2025-04-15', 25.00),
(2010, 45, '2025-04-14', 7.50),
(2011, 50, '2025-04-13', 11.25),
(2012, 55, '2025-04-12', 19.99),
(2013, 60, '2025-04-11', 6.80),
(2014, 65, '2025-04-10', 13.50),
(2015, 1, '2025-04-09', 21.00),
(2016, 5, '2025-04-08', 8.99),
(2017, 10, '2025-04-07', 16.20),
(2018, 15, '2025-04-06', 12.50),
(2019, 20, '2025-04-05', 9.75),
(2020, 25, '2025-04-04', 17.00),
(2021, 30, '2025-04-03', 11.11),
(2022, 35, '2025-04-02', 23.45),
(2023, 40, '2025-04-01', 8.88),
(2024, 45, '2025-03-31', 15.75),
(2025, 50, '2025-03-30', 20.20),
(2026, 55, '2025-03-29', 7.77),
(2027, 60, '2025-03-28', 14.44),
(2028, 65, '2025-03-27', 19.19),
(2029, 1, '2025-03-26', 10.10),
(2030, 5, '2025-03-25', 17.17),
(2031, 10, '2025-03-24', 13.13),
(2032, 15, '2025-03-23', 21.21),
(2033, 20, '2025-03-22', 9.09),
(2034, 25, '2025-03-21', 16.00),
(2035, 30, '2025-03-20', 12.22),
(2036, 35, '2025-03-19', 24.24),
(2037, 40, '2025-03-18', 6.66),
(2038, 45, '2025-03-17', 18.18),
(2039, 50, '2025-03-16', 11.50),
(2040, 55, '2025-03-15', 22.50),
(2041, 60, '2025-03-14', 15.50),
(2042, 65, '2025-03-13', 19.50),
(2043, 1, '2025-03-12', 13.00),
(2044, 5, '2025-03-11', 21.50),
(2045, 10, '2025-03-10', 16.50),
(2046, 15, '2025-03-09', 10.00),
(2047, 20, '2025-03-08', 23.00),
(2048, 25, '2025-03-07', 17.50),
(2049, 30, '2025-03-06', 14.00),
(2050, 35, '2025-03-05', 20.00);

-- inserting the datas for the column in a table
INSERT INTO payment (payment_id, purchase_id, method, status, payment_date) VALUES
(3001, 2051, 'Credit Card', 'Completed', '2025-04-23 10:00:00'),
(3002, 2052, 'PayPal', 'Completed', '2025-04-22 15:30:00'),
(3003, 2053, 'Debit Card', 'Completed', '2025-04-21 09:15:00'),
(3004, 2054, 'Credit Card', 'Completed', '2025-04-20 18:00:00'),
(3005, 2055, 'Apple Pay', 'Completed', '2025-04-19 12:45:00'),
(3006, 2056, 'Google Pay', 'Completed', '2025-04-18 11:00:00'),
(3007, 2057, 'Credit Card', 'Completed', '2025-04-17 14:20:00'),
(3008, 2058, 'PayPal', 'Completed', '2025-04-16 20:00:00'),
(3009, 2059, 'Debit Card', 'Completed', '2025-04-15 08:00:00'),
(3010, 2060, 'Credit Card', 'Completed', '2025-04-14 16:30:00'),
(3011, 2061, 'Apple Pay', 'Completed', '2025-04-13 13:00:00'),
(3012, 2062, 'Google Pay', 'Completed', '2025-04-12 09:00:00'),
(3013, 2063, 'Credit Card', 'Completed', '2025-04-11 17:15:00'),
(3014, 2064, 'PayPal', 'Completed', '2025-04-10 19:45:00'),
(3015, 2065, 'Debit Card', 'Completed', '2025-04-09 10:30:00'),
(3016, 2066, 'Credit Card', 'Completed', '2025-04-08 14:00:00'),
(3017, 2067, 'Apple Pay', 'Completed', '2025-04-07 11:45:00'),
(3018, 2068, 'Google Pay', 'Completed', '2025-04-06 12:00:00'),
(3019, 2069, 'Credit Card', 'Completed', '2025-04-05 15:00:00'),
(3020, 2070, 'PayPal', 'Completed', '2025-04-04 18:30:00'),
(3021, 2071, 'Debit Card', 'Completed', '2025-04-03 07:30:00'),
(3022, 2072, 'Credit Card', 'Completed', '2025-04-02 21:00:00'),
(3023, 2073, 'Apple Pay', 'Completed', '2025-04-01 13:30:00'),
(3024, 2074, 'Google Pay', 'Completed', '2025-03-31 10:00:00'),
(3025, 2075, 'Credit Card', 'Completed', '2025-03-30 16:00:00'),
(3026, 2076, 'PayPal', 'Completed', '2025-03-29 19:00:00'),
(3027, 2077, 'Debit Card', 'Completed', '2025-03-28 08:30:00'),
(3028, 2078, 'Credit Card', 'Completed', '2025-03-27 11:30:00'),
(3029, 2079, 'Apple Pay', 'Completed', '2025-03-26 14:30:00'),
(3030, 2080, 'Google Pay', 'Completed', '2025-03-25 17:30:00'),
(3031, 2081, 'Credit Card', 'Completed', '2025-03-24 20:30:00'),
(3032, 2082, 'PayPal', 'Completed', '2025-03-23 09:30:00'),
(3033, 2083, 'Debit Card', 'Completed', '2025-03-22 12:30:00'),
(3034, 2084, 'Credit Card', 'Completed', '2025-03-21 15:30:00'),
(3035, 2085, 'Apple Pay', 'Completed', '2025-03-20 18:30:00'),
(3036, 2086, 'Google Pay', 'Completed', '2025-03-19 07:00:00'),
(3037, 2087, 'Credit Card', 'Completed', '2025-03-18 10:00:00'),
(3038, 2088, 'PayPal', 'Completed', '2025-03-17 13:00:00'),
(3039, 2089, 'Debit Card', 'Completed', '2025-03-16 16:00:00'),
(3040, 2090, 'Credit Card', 'Completed', '2025-03-15 19:00:00'),
(3041, 2091, 'Apple Pay', 'Completed', '2025-03-14 08:00:00'),
(3042, 2092, 'Google Pay', 'Completed', '2025-03-13 11:00:00'),
(3043, 2093, 'Credit Card', 'Completed', '2025-03-12 14:00:00'),
(3044, 2094, 'PayPal', 'Completed', '2025-03-11 17:00:00'),
(3045, 2095, 'Debit Card', 'Completed', '2025-03-10 20:00:00'),
(3046, 2096, 'Credit Card', 'Completed', '2025-03-09 09:00:00'),
(3047, 2097, 'Apple Pay', 'Completed', '2025-03-08 12:00:00'),
(3048, 2098, 'Google Pay', 'Completed', '2025-03-07 15:00:00'),
(3049, 2099, 'Credit Card', 'Completed', '2025-03-06 18:00:00'),
(3050, 2100, 'PayPal', 'Completed', '2025-03-05 07:00:00');

-- inserting the datas for the column in a table
INSERT INTO playlist (playlist_id, name, customer_id, created_at) VALUES
(4001, 'My Favorites', 1, '2025-04-23 09:00:00'),
(4002, 'Workout Mix', 5, '2025-04-22 14:30:00'),
(4003, 'Chill Vibes', 10, '2025-04-21 18:00:00'),
(4004, 'Road Trip Songs', 15, '2025-04-20 11:00:00'),
(4005, 'Party Anthems', 20, '2025-04-19 20:00:00'),
(4006, 'Acoustic Covers', 25, '2025-04-18 08:30:00'),
(4007, 'Throwback Tunes', 30, '2025-04-17 16:00:00'),
(4008, 'Indie Gems', 35, '2025-04-16 12:00:00'),
(4009, 'Relaxing Piano', 40, '2025-04-15 22:00:00'),
(4010, 'Hip Hop Hits', 45, '2025-04-14 07:00:00'),
(4011, 'Country Classics', 50, '2025-04-13 19:00:00'),
(4012, 'Jazz Standards', 55, '2025-04-12 13:30:00'),
(4013, 'Rock Legends', 60, '2025-04-11 10:30:00'),
(4014, '90s Pop', 1, '2025-04-10 21:00:00'),
(4015, '00s Hits', 5, '2025-04-09 06:00:00'),
(4016, 'Current Favorites', 10, '2025-04-08 17:00:00'),
(4017, 'Dance Party', 15, '2025-04-07 11:30:00'),
(4018, 'Study Music', 20, '2025-04-06 23:00:00'),
(4019, 'Morning Boost', 25, '2025-04-05 09:30:00'),
(4020, 'Evening Wind Down', 30, '2025-04-04 15:00:00'),
(4021, 'Focus Tracks', 35, '2025-04-03 13:00:00'),
(4022, 'Upbeat Instrumentals', 40, '2025-04-02 20:30:00'),
(4023, 'Mellow Vibes', 45, '2025-04-01 08:00:00'),
(4024, 'Throwback R&B', 50, '2025-03-31 16:30:00'),
(4025, 'Guilty Pleasures', 55, '2025-03-30 14:00:00'),
(4026, 'Global Sounds', 60, '2025-03-29 22:30:00'),
(4027, 'Summer Hits', 1, '2025-03-28 07:30:00'),
(4028, 'Winter Warmers', 5, '2025-03-27 19:30:00'),
(4029, 'Spring Fling', 10, '2025-03-26 11:30:00'),
(4030, 'Autumn Moods', 15, '2025-03-25 21:30:00'),
(4031, 'Movie Soundtracks', 20, '2025-03-24 06:30:00'),
(4032, 'Game Music', 25, '2025-03-23 18:30:00'),
(4033, 'Classical Study', 30, '2025-03-22 10:30:00'),
(4034, 'Acoustic Chill', 35, '2025-03-21 20:30:00'),
(4035, 'Energetic Pop', 40, '2025-03-20 05:30:00'),
(4036, 'Latin Grooves', 45, '2025-03-19 17:30:00'),
(4037, 'Reggae Relax', 50, '2025-03-18 12:30:00'),
(4038, 'Bluesy Nights', 55, '2025-03-17 23:30:00'),
(4039, 'Folk Tales', 60, '2025-03-16 09:30:00'),
(4040, 'Indie Pop', 1, '2025-03-15 15:30:00'),
(4041, 'Alt Rock', 5, '2025-03-14 06:30:00'),
(4042, 'Metal Madness', 10, '2025-03-13 18:30:00'),
(4043, 'Punk Power', 15, '2025-03-12 13:30:00'),
(4044, 'Disco Fever', 20, '2025-03-11 22:30:00'),
(4045, 'Funk Fusion', 25, '2025-03-10 08:30:00'),
(4046, 'Soulful Sounds', 30, '2025-03-09 16:30:00'),
(4047, 'Gospel Glory', 35, '2025-03-08 11:30:00'),
(4048, 'Opera Obsession', 40, '2025-03-07 23:30:00'),
(4049, 'Symphonic Stories', 45, '2025-03-06 09:30:00'),
(4050, 'Concerto Collection', 50, '2025-03-05 17:30:00');

-- inserting the datas for the column in a table
INSERT INTO song (song_id, title, duration, price, album_id, genre_id) VALUES
(5001, 'Lost in the Echo', '00:03:25', 1.29, 324, 202),   -- Linkin Park, Rock
(5002, 'Numb', '00:03:07', 0.99, 324, 202),
(5003, 'In the End', '00:03:36', 1.49, 324, 202),
(5004, 'What I\'ve Done', '00:03:25', 1.29, 324, 202),
(5005, 'Crawling', '00:04:29', 0.99, 324, 202),
(5006, 'Perfect', '00:04:23', 1.29, 312, 201),      -- Ed Sheeran, Pop
(5007, 'Shape of You', '00:03:53', 1.29, 312, 201),
(5008, 'Thinking Out Loud', '00:04:41', 0.99, 312, 201),
(5009, 'Castle on the Hill', '00:04:21', 1.29, 312, 201),
(5010, 'The A Team', '00:04:18', 0.99, 312, 201),
(5011, 'Bohemian Rhapsody', '00:05:55', 1.99, 325, 202), -- Queen, Rock
(5012, 'Somebody to Love', '00:04:56', 1.49, 325, 202),
(5013, 'Don\'t Stop Me Now', '00:03:29', 1.29, 325, 202),
(5014, 'We Will Rock You', '00:02:01', 0.99, 325, 202),
(5015, 'We Are the Champions', '00:03:01', 1.29, 325, 202),
(5016, 'Starboy', '00:03:50', 1.29, 318, 204),       -- The Weeknd, R&B
(5017, 'Blinding Lights', '00:03:20', 1.29, 318, 204),
(5018, 'Can\'t Feel My Face', '00:03:35', 0.99, 318, 204),
(5019, 'The Hills', '00:04:02', 1.29, 318, 204),
(5020, 'Often', '00:04:09', 0.99, 318, 204),
(5021, 'Bad Guy', '00:03:14', 1.29, 319, 201),       -- Billie Eilish, Pop
(5022, 'Bury a Friend', '00:03:13', 0.99, 319, 201),
(5023, 'Ocean Eyes', '00:04:31', 1.29, 319, 201),
(5024, 'Lovely (with Khalid)', '00:03:20', 1.29, 319, 201),
(5025, 'When the Party\'s Over', '00:03:16', 0.99, 319, 201),
(5026, 'Dynamite', '00:03:19', 1.29, 331, 237),      -- BTS, K-Pop
(5027, 'Boy With Luv (feat. Halsey)', '00:04:12', 1.29, 331, 237),
(5028, 'Spring Day', '00:04:34', 0.99, 331, 237),
(5029, 'Fake Love', '00:04:02', 1.29, 331, 237),
(5030, 'IDOL', '00:03:43', 0.99, 331, 237),
(5031, 'Kill This Love', '00:03:09', 1.29, 332, 237),  -- Blackpink, K-Pop
(5032, 'How You Like That', '00:03:00', 1.29, 332, 237),
(5033, 'DDU-DU DDU-DU', '00:03:14', 0.99, 332, 237),
(5034, 'Lovesick Girls', '00:03:12', 1.29, 332, 237),
(5035, 'Playing With Fire', '00:03:17', 0.99, 332, 237),
(5036, 'Perfect', '00:04:20', 1.29, 345, 240),      -- Armaan Malik, Bollywood
(5037, 'Butta Bomma', '00:03:21', 1.29, 345, 240),
(5038, 'Tum Hi Ho', '00:04:22', 0.99, 345, 240),
(5039, 'Kaun Tujhe', '00:03:09', 1.29, 345, 240),
(5040, 'Wajah Tum Ho', '00:03:23', 0.99, 345, 240),
(5041, 'Channa Mereya', '00:04:48', 1.49, 349, 240),  -- Pritam, Bollywood
(5042, 'Ae Dil Hai Mushkil', '00:04:29', 1.29, 349, 240),
(5043, 'Kabira', '00:03:40', 0.99, 349, 240),
(5044, 'Kesariya', '00:04:28', 1.29, 349, 240),
(5045, 'The Breakup Song', '00:04:10', 0.99, 349, 240),
(5046, 'Kun Faya Kun', '00:07:51', 1.99, 350, 240),  -- AR Rahman, Bollywood
(5047, 'Maa Tujhe Salaam', '00:02:15', 1.49, 350, 240),
(5048, 'Jai Ho', '00:05:34', 1.29, 350, 240),
(5049, 'Dil Se Re', '00:06:47', 0.99, 350, 240),
(5050, 'Tu Hi Re', '00:05:13', 1.29, 350, 240);

-- inserting the datas for the column in a table
INSERT INTO playlistSong (playlist_id, song_id) VALUES
(4001, 5001),
(4002, 5002),
(4003, 5003),
(4004, 5004),
(4005, 5005),
(4006, 5006),
(4007, 5007),
(4008, 5008),
(4009, 5009),
(4010, 5010),
(4011, 5011),
(4012, 5012),
(4013, 5013),
(4014, 5014),
(4015, 5015),
(4016, 5016),
(4017, 5017),
(4018, 5018),
(4019, 5019),
(4020, 5020),
(4021, 5021),
(4022, 5022),
(4023, 5023),
(4024, 5024),
(4025, 5025),
(4026, 5026),
(4027, 5027),
(4028, 5028),
(4029, 5029),
(4030, 5030),
(4031, 5031),
(4032, 5032),
(4033, 5033),
(4034, 5034),
(4035, 5035),
(4036, 5036),
(4037, 5037),
(4038, 5038),
(4039, 5039),
(4040, 5040),
(4041, 5041),
(4042, 5042),
(4043, 5043),
(4044, 5044),
(4045, 5045),
(4046, 5046),
(4047, 5047),
(4048, 5048),
(4049, 5049),
(4050, 5050);

-- inserting the datas for the column in a table
INSERT INTO PurchaseDetail (purchase_id, song_id) VALUES
(2051, 5001),
(2051, 5006),
(2051, 5011),
(2052, 5016),
(2052, 5021),
(2053, 5026),
(2053, 5031),
(2053, 5036),
(2054, 5041),
(2055, 5046),
(2056, 5002),
(2056, 5007),
(2057, 5012),
(2057, 5017),
(2057, 5022),
(2058, 5027),
(2058, 5032),
(2058, 5037),
(2059, 5042),
(2059, 5047),
(2060, 5003),
(2060, 5008),
(2060, 5013),
(2061, 5018),
(2061, 5023),
(2061, 5028),
(2062, 5033),
(2062, 5038),
(2062, 5043),
(2063, 5048),
(2064, 5004),
(2064, 5009),
(2064, 5014),
(2065, 5019),
(2065, 5024),
(2065, 5029),
(2066, 5034),
(2066, 5039),
(2066, 5044),
(2067, 5049),
(2068, 5005),
(2068, 5010),
(2068, 5015),
(2069, 5020),
(2069, 5025),
(2069, 5030),
(2070, 5035),
(2070, 5040),
(2070, 5045),
(2070, 5050),
(2071, 5001),
(2071, 5011),
(2071, 5021),
(2072, 5031),
(2073, 5041),
(2074, 5006),
(2074, 5016),
(2074, 5026),
(2075, 5036),
(2076, 5002),
(2076, 5012),
(2076, 5022),
(2077, 5032),
(2077, 5042),
(2078, 5007),
(2078, 5017),
(2078, 5027),
(2079, 5037),
(2080, 5047),
(2081, 5003),
(2081, 5013),
(2081, 5023),
(2082, 5033),
(2082, 5043),
(2083, 5008),
(2083, 5018),
(2083, 5028),
(2084, 5038),
(2084, 5048),
(2085, 5004),
(2085, 5014),
(2085, 5024),
(2086, 5034),
(2086, 5044),
(2087, 5009),
(2087, 5019),
(2087, 5029),
(2088, 5039),
(2088, 5049),
(2089, 5005),
(2089, 5010),
(2089, 5015),
(2090, 5020),
(2090, 5025),
(2090, 5030),
(2091, 5035),
(2091, 5040),
(2091, 5045),
(2091, 5050),
(2092, 5001),
(2092, 5002),
(2092, 5003),
(2092, 5004),
(2093, 5005),
(2093, 5006),
(2093, 5007),
(2093, 5008),
(2093, 5009),
(2094, 5010),
(2094, 5011),
(2094, 5012),
(2094, 5013),
(2094, 5014),
(2095, 5015),
(2095, 5016),
(2095, 5017),
(2095, 5018),
(2095, 5019);

-- inserting the datas for the column in a table
INSERT INTO Review (customer_id, song_id, rating, comment, review_date) VALUES
(1, 5001, 4, 'Great song, love the energy!', '2025-04-24 10:00:00'),
(5, 5006, 5, 'This is my new favorite song!', '2025-04-23 15:30:00'),
(10, 5011, 3, 'Not bad, but not my usual style.', '2025-04-22 09:15:00'),
(15, 5016, 2, 'I didn\'t really enjoy this one.', '2025-04-21 18:00:00'),
(20, 5021, 5, 'Absolutely amazing!', '2025-04-20 12:45:00'),
(25, 5026, 4, 'Catchy tune.', '2025-04-19 11:00:00'),
(30, 5031, 3, 'It\'s okay.', '2025-04-18 14:20:00'),
(35, 5036, 5, 'Beautiful song.', '2025-04-17 20:00:00'),
(40, 5041, 4, 'Good music.', '2025-04-16 08:00:00'),
(45, 5046, 5, 'Incredible!', '2025-04-15 16:30:00'),
(50, 5002, 3, 'Average song.', '2025-04-14 13:00:00'),
(55, 5007, 4, 'Nice melody.', '2025-04-13 09:00:00'),
(60, 5012, 5, 'Classic!', '2025-04-12 17:15:00'),
(1, 5017, 2, 'Not a fan.', '2025-04-11 19:45:00'),
(5, 5022, 4, 'Enjoyable.', '2025-04-10 10:30:00'),
(10, 5027, 5, 'Love this group!', '2025-04-09 14:00:00'),
(15, 5032, 3, 'Decent.', '2025-04-08 11:45:00'),
(20, 5037, 4, 'Great vocals.', '2025-04-07 12:00:00'),
(25, 5042, 5, 'Awesome!', '2025-04-06 15:00:00'),
(30, 5047, 3, 'Not bad.', '2025-04-05 18:30:00'),
(35, 5003, 4, 'Good rhythm.', '2025-04-04 07:30:00'),
(40, 5008, 5, 'So catchy!', '2025-04-03 21:00:00'),
(45, 5013, 2, 'Disappointing.', '2025-04-02 13:30:00'),
(50, 5018, 4, 'Pretty good.', '2025-04-01 10:00:00'),
(55, 5023, 5, 'Amazing lyrics.', '2025-03-31 16:00:00'),
(60, 5028, 3, 'Could be better.', '2025-03-30 19:00:00'),
(1, 5033, 4, 'I like it.', '2025-03-29 08:30:00'),
(5, 5038, 5, 'Fantastic!', '2025-03-28 11:30:00'),
(10, 5043, 2, 'Waste of time.', '2025-03-27 14:30:00'),
(15, 5048, 4, 'Really nice.', '2025-03-26 17:30:00'),
(20, 5004, 5, 'Best song ever!', '2025-03-25 20:30:00'),
(25, 5009, 3, 'Okay, I guess.', '2025-03-24 09:30:00'),
(30, 5014, 4, 'Great beat.', '2025-03-23 12:30:00'),
(35, 5019, 5, 'Excellent!', '2025-03-22 15:30:00'),
(40, 5024, 2, 'Terrible.', '2025-03-21 18:30:00'),
(45, 5029, 4, 'Not bad at all.', '2025-03-20 07:00:00'),
(50, 5034, 5, 'So good!', '2025-03-19 10:00:00'),
(55, 5039, 3, 'Meh.', '2025-03-18 13:00:00'),
(60, 5044, 4, 'Pretty cool.', '2025-03-17 16:00:00'),
(1, 5049, 5, 'Absolutely love it!', '2025-03-16 19:00:00'),
(5, 5005, 4, 'Really enjoyed it.', '2025-03-15 08:00:00'),
(10, 5010, 3, 'Not my cup of tea.', '2025-03-14 11:00:00'),
(15, 5015, 5, 'A masterpiece!', '2025-03-13 14:00:00'),
(20, 5020, 2, 'Hated it.', '2025-03-12 17:00:00'),
(25, 5025, 4, 'Decent track.', '2025-03-11 20:00:00'),
(30, 5030, 5, 'Amazing song writing.', '2025-03-10 09:00:00'),
(35, 5035, 3, 'Nothing special.', '2025-03-09 12:00:00'),
(40, 5040, 4, 'Quite good.', '2025-03-08 15:00:00'),
(45, 5045, 5, 'A true gem!', '2025-03-07 18:00:00'),
(50, 5050, 4, 'Lovely melody.', '2025-03-06 07:00:00');

-- inserting the datas for the column in a table
INSERT INTO Subscription (customer_id, plan, start_date, end_date, is_active) VALUES
(1, 'Premium', '2025-04-23', '2026-04-23', 1),
(5, 'Basic', '2025-04-22', '2025-05-22', 1),
(10, 'Family', '2025-04-21', '2026-04-21', 1),
(15, 'Premium', '2025-04-20', '2025-05-20', 0),
(20, 'Basic', '2025-04-19', '2025-06-19', 1),
(25, 'Family', '2025-04-18', '2026-04-18', 1),
(30, 'Premium', '2025-04-17', '2025-05-17', 0),
(35, 'Basic', '2025-04-16', '2025-07-16', 1),
(40, 'Family', '2025-04-15', '2026-04-15', 1),
(45, 'Premium', '2025-04-14', '2025-05-14', 1),
(50, 'Basic', '2025-04-13', '2025-08-13', 1),
(55, 'Family', '2025-04-12', '2026-04-12', 1),
(60, 'Premium', '2025-04-11', '2025-05-11', 0),
(1, 'Basic', '2025-04-10', '2025-09-10', 1),
(5, 'Family', '2025-04-09', '2026-04-09', 1),
(10, 'Premium', '2025-04-08', '2025-05-08', 1),
(15, 'Basic', '2025-04-07', '2025-10-07', 1),
(20, 'Family', '2025-04-06', '2026-04-06', 1),
(25, 'Premium', '2025-04-05', '2025-05-05', 0),
(30, 'Basic', '2025-04-04', '2025-11-04', 1),
(35, 'Family', '2025-04-03', '2026-04-03', 1),
(40, 'Premium', '2025-04-02', '2025-05-02', 1),
(45, 'Basic', '2025-04-01', '2025-12-01', 1),
(50, 'Family', '2025-03-31', '2026-03-31', 1),
(55, 'Premium', '2025-03-30', '2025-04-30', 0),
(60, 'Basic', '2025-03-29', '2025-07-29', 1),
(1, 'Family', '2025-03-28', '2026-03-28', 1),
(5, 'Premium', '2025-03-27', '2025-04-27', 1),
(10, 'Basic', '2025-03-26', '2025-06-26', 1),
(15, 'Family', '2025-03-25', '2026-03-25', 1),
(20, 'Premium', '2025-03-24', '2025-04-24', 0),
(25, 'Basic', '2025-03-23', '2025-08-23', 1),
(30, 'Family', '2025-03-22', '2026-03-22', 1),
(35, 'Premium', '2025-03-21', '2025-04-21', 1),
(40, 'Basic', '2025-03-20', '2025-09-20', 1),
(45, 'Family', '2025-03-19', '2026-03-19', 1),
(50, 'Premium', '2025-03-18', '2025-04-18', 0),
(55, 'Basic', '2025-03-17', '2025-10-17', 1),
(60, 'Family', '2025-03-16', '2026-03-16', 1),
(1, 'Premium', '2025-03-15', '2025-04-15', 1),
(5, 'Basic', '2025-03-14', '2025-11-14', 1),
(10, 'Family', '2025-03-13', '2026-03-13', 1),
(15, 'Premium', '2025-03-12', '2025-04-12', 0),
(20, 'Basic', '2025-03-11', '2025-12-11', 1),
(25, 'Family', '2025-03-10', '2026-03-10', 1),
(30, 'Premium', '2025-03-09', '2025-04-09', 1),
(35, 'Basic', '2025-03-08', '2025-08-08', 1),
(40, 'Family', '2025-03-07', '2026-03-07', 1),
(45, 'Premium', '2025-03-06', '2025-04-06', 1),
(50, 'Basic', '2025-03-05', '2025-07-05', 1);

DELIMITER //
-- returns all the names of the playlists created by that customer--
CREATE PROCEDURE GetCustomerPlaylists (
    IN p_customer_id INT
)
BEGIN
    SELECT playlist_id, name, created_at
    FROM playlist
    WHERE customer_id = p_customer_id;
END //
DELIMITER ;
call GetCustomerPlaylists(15);

-- returns the title and artist name of all songs within that playlist
DELIMITER //
CREATE PROCEDURE GetSongsInPlaylist (
    IN playlistId INT
)
BEGIN
    SELECT s.title, ar.name AS artist_name
    FROM playlistsong ps
    JOIN song s ON ps.song_id = s.song_id
    JOIN album al ON s.album_id = al.album_id
    JOIN artist ar ON al.artist_id = ar.artist_id
    WHERE ps.playlist_id = playlistId;
END //
DELIMITER ;
call GetSongsInPlaylist(4005);

-- returns the titles and release years of all albums by that artist
DELIMITER //
CREATE PROCEDURE GetArtistAlbums (
    IN art_id INT
)
BEGIN
    SELECT a.title, a.release_year
    FROM album a
    WHERE a.artist_id = art_id;
END //
DELIMITER ;
CALL GetArtistAlbums(104); 

-- returns the titles of all songs belonging to that genre
DELIMITER //
CREATE PROCEDURE GetGenreSongs (
    IN genreName VARCHAR(50)
)
BEGIN
    SELECT s.title
    FROM song s
    JOIN genre g ON s.genre_id = g.genre_id
    WHERE g.name = genreName;
END //
DELIMITER ;
CALL GetGenreSongs('Pop');


 --  inserts a new record
	DELIMITER //

CREATE PROCEDURE UpdatePurchaseAmount (
    IN custId INT,
    IN purchaseDate DATE,
    IN newTotalAmount DECIMAL(8,2)
)
BEGIN
    UPDATE purchase
    SET total_amount = newTotalAmount
    WHERE customer_id = custId
      AND purchase_date = purchaseDate;
END //

DELIMITER ;
CALL UpdatePurchaseAmount(custId_value, purchaseDate_value, newTotalAmount_value);

-- check if the song already exists If it doesn't, it should add the song
DELIMITER //
CREATE PROCEDURE AddSongToPlaylist (
    IN playlistId INT,
    IN songId INT
)
BEGIN
    -- Check if the song already exists in the playlist
    IF NOT EXISTS (SELECT 1 FROM playlistsong WHERE playlist_id = playlistId AND song_id = songId) THEN
        -- Insert the song into the playlist
        INSERT INTO playlistsong (playlist_id, song_id)
        VALUES (playlistId, songId);
    END IF;
END //
DELIMITER ;
CALL AddSongToPlaylist(10, 4003);

-- ordered by the purchase date in descending order
DELIMITER //
CREATE PROCEDURE GetCustomerPurchaseHistory (
    IN custId INT
)
BEGIN
    SELECT purchase_id, purchase_date, total_amount
    FROM purchase
    WHERE customer_id = custId
    ORDER BY purchase_date DESC;
END //
DELIMITER ;
call GetCustomerPurchaseHistory(5);

-- returns the titles of all songs by that artist belonging to that genre
DELIMITER //
CREATE PROCEDURE GetSongsByArtistAndGenre (
    IN artistName VARCHAR(100),
    IN genreName VARCHAR(50)
)
BEGIN
    SELECT s.title
    FROM song s
    JOIN album a ON s.album_id = a.album_id
    JOIN artist ar ON a.artist_id = ar.artist_id
    JOIN genre g ON s.genre_id = g.genre_id
    WHERE ar.name = artistName AND g.name = genreName;
END //
DELIMITER ;
CALL GetSongsByArtistAndGenre('Taylor Swift', 'Pop');

-- returns the average rating for that song
DELIMITER //
CREATE PROCEDURE GetAverageRatingForSong (
    IN songId INT,
    OUT avgRating DECIMAL(3, 2)
)
BEGIN
    SELECT AVG(rating) INTO avgRating
    FROM review
    WHERE song_id = songId;
END //
DELIMITER ;
CALL GetAverageRatingForSong(4006, @average_rating); 
SELECT @average_rating; 

-- return  subscriptions that are currently active
DELIMITER //
CREATE PROCEDURE GetActiveSubscriptions ()
BEGIN
    SELECT customer_id, plan
    FROM subscription
    WHERE is_active = 1 AND CURRENT_DATE BETWEEN start_date AND end_date;
END //
DELIMITER ;
call GetActiveSubscriptions();
