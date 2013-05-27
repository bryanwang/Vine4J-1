#### Error Codes ####
(101) URL is empty 
(102) Tag seacrh term is empty
(103) Authenticate first
(104) Server return empty data
(105) Server returns Error ...
(106) Server return empty data
(107) Server return empty data
(108) Server return empty data
(109) User seacrh term is empty
(110) User Id is empty
(111) (username and password) or (key) must be set
(112) Authenticate error
(113) Url doesn't belong to vine check your url
(114) Vine service is empty
(115) User id is not valid 
(116) Password is empty
(117) Password must at least 4 character
(118) Username is empty
(119) Username must at least 4 character
(120) Email is empty
(121) Email is valid


#### Next features ####
video post etme



def upload(self, videoData, thumbData, description):
        cid = self._contentId()
        self._postForm('/posts',
            videoUrl = self.s3.put('/videos/%s.mp4' % cid, 'video/mp4', videoData),
            thumbnailUrl = self.s3.put('/thumbs/%s.mp4.jpg' % cid, 'image/jpeg', thumbData),
            description = description
        )
        return cid